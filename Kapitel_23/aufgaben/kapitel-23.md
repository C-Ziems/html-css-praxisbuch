# Aufgaben und Lösungsvorschläge zu Kapitel 23: Flexbox

## Aufgabe 1

**Aufgabe:** Eine Fußzeile enthält drei Links: Zwei stehen links, der dritte rechts abgesetzt, und bei Platzmangel brechen sie um. Gestalte die Fußzeile mit Flexbox.

**Lösungsvorschlag**

```html
<footer class="fusszeile">
    <a href="kontakt.html">Kontakt</a>
    <a href="hilfe.html">Hilfe</a>
    <a class="nach-oben" href="#seitenanfang">Nach oben</a>
</footer>
```

```css
.fusszeile {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
}

.nach-oben {
    margin-inline-start: auto;
}
```

Der automatische Außenabstand nimmt den freien Raum vor dem dritten Link auf und setzt ihn nach rechts ab. `flex-wrap: wrap` erlaubt einen Umbruch bei Platzmangel.

## Aufgabe 2

**Aufgabe:** Ein Link erhält `order: -1`. Erkläre, warum er dadurch optisch nach vorn rückt, die Tastaturreihenfolge aber nicht ändert, und wann das zum Problem wird.

**Lösungsvorschlag**

`order` verändert nur die sichtbare Anordnung. Die Reihenfolge im DOM bleibt gleich, und nach ihr richten sich Tabulatortaste und Screenreader. Steht ein Link sichtbar vorn, wird aber erst zuletzt fokussiert, springt der Fokus scheinbar ungeordnet über die Seite. Das verwirrt besonders Menschen, die mit der Tastatur arbeiten und gleichzeitig auf den Bildschirm sehen. Soll die Reihenfolge für alle gelten, ändern wir sie im HTML.
