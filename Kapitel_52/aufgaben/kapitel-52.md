# Aufgaben und Lösungsvorschläge zu Kapitel 52: Scrollgesteuerte Animationen und View Transitions

## Aufgabe 1

**Aufgabe:** Eine Leiste soll den Lesefortschritt zeigen und mit dem Scrollen der Seite von 0 auf volle Breite wachsen. Sie erscheint nur bei Unterstützung und ohne Präferenz für reduzierte Bewegung. Schreibe HTML und CSS.

**Lösungsvorschlag**

```html
<div class="lesefortschritt" aria-hidden="true"></div>
```

```css
.lesefortschritt {
    display: none;
}

@keyframes lesefortschritt {
    from { transform: scaleX(0); }
    to   { transform: scaleX(1); }
}

@supports (animation-timeline: scroll()) {
    @media (prefers-reduced-motion: no-preference) {
        .lesefortschritt {
            display: block;
            position: fixed;
            inset-block-start: 0;
            inset-inline: 0;
            block-size: 0.25rem;
            background-color: var(--farbe-akzent);
            transform-origin: left;
            animation: lesefortschritt linear;
            animation-timeline: scroll(root);
        }
    }
}
```

`animation-timeline` steht nach der Kurzschreibweise `animation`, weil diese die Timeline zurücksetzt. Die Leiste ist rein dekorativ und deshalb für assistive Technik ausgeblendet.

## Aufgabe 2

**Aufgabe:** Scrollgesteuerte Animationen können `scroll()` oder `view()` verwenden. Erkläre den Unterschied an je einem Beispiel.

**Lösungsvorschlag**

`scroll()` verbindet den Fortschritt mit der Scrollposition eines Scrollcontainers, etwa der ganzen Seite: Die Lesefortschrittsleiste aus Aufgabe 1 ist am Seitenanfang leer und am Seitenende voll. `view()` verbindet den Fortschritt mit der Position eines Elements im sichtbaren Bereich: Ein Bild kann sich beispielsweise einblenden, während es von unten in den Viewport hineinscrollt.
