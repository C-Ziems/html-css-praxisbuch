# Aufgaben und Lösungsvorschläge zu Kapitel 25: CSS Grid: Elemente platzieren und Subgrid nutzen

## Aufgabe 1

**Aufgabe:** Ein Seitenlayout besteht aus einem Kopf über die ganze Breite, Navigation links, Inhalt rechts und einem Fuß über die ganze Breite. Beschreibe es mit `grid-template-areas`.

**Lösungsvorschlag**

```css
.seite {
    display: grid;
    grid-template-columns: 12rem 1fr;
    grid-template-areas:
        "kopf kopf"
        "navigation inhalt"
        "fuss fuss";
    gap: 1rem;
}

.seite > header { grid-area: kopf; }
.seite > nav    { grid-area: navigation; }
.seite > main   { grid-area: inhalt; }
.seite > footer { grid-area: fuss; }
```

Jede Zeichenkette beschreibt eine Rasterzeile. Ein Name, der in mehreren Zellen steht, bildet einen zusammenhängenden Bereich.

## Aufgabe 2

**Aufgabe:** Eine Liste von Karten verwendet `grid-auto-flow: dense`. Erkläre, warum das problematisch sein kann.

**Lösungsvorschlag**

`dense` füllt Lücken mit späteren Items, die hineinpassen. Dadurch kann eine Karte sichtbar vor einer anderen stehen, obwohl sie im DOM später folgt. Lesereihenfolge und Tastaturreihenfolge richten sich weiter nach dem DOM, der Fokus springt dann scheinbar ungeordnet. Bei Inhalten mit sinnvoller Reihenfolge verzichten wir deshalb auf `dense`.
