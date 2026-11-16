# Aufgaben und Lösungsvorschläge zu Kapitel 60: Validierung, Kompatibilität und @supports

## Aufgabe 1

**Aufgabe:** Der Nu Html Checker meldet zu `<p><h3>Hinweis</h3> Text</p>`: „No p element in scope but a p end tag seen.“ Erkläre, wie diese Meldung entsteht, und korrigiere den Ausschnitt.

**Lösungsvorschlag**

Ein Absatz darf keine Überschrift enthalten. Beim Einlesen beendet der Browser den Absatz deshalb automatisch, sobald `<h3>` beginnt. Das spätere `</p>` findet keinen offenen Absatz mehr, daher die Meldung. Im DOM entstehen ein leerer Absatz, die Überschrift, der Text außerhalb eines Absatzes und ein weiterer leerer Absatz.

```html
<h3>Hinweis</h3>
<p>Text</p>
```

## Aufgabe 2

**Aufgabe:** Eine Kartenliste ist bereits ein Grid mit mehreren Spalten. Jede Karte besteht aus Überschrift, Text und Fußbereich und soll diese drei Teile mit `subgrid` an gemeinsamen Zeilen der Liste ausrichten. Ohne Unterstützung für `subgrid` behält sie ihr einfaches Layout. Schreibe die Regel mit `@supports`.

**Lösungsvorschlag**

```css
@supports (grid-template-rows: subgrid) {
    .karte {
        display: grid;
        grid-row: span 3;
        grid-template-rows: subgrid;
    }
}
```

Das Raster der Kartenliste legt die Spalten fest; ihre Zeilen entstehen implizit. Jede Karte überspannt mit `grid-row: span 3` drei dieser Zeilen, eine je Bestandteil, und übernimmt sie mit `grid-template-rows: subgrid`. Erst dieses Zusammenspiel richtet die Inhalte aus; `@supports` allein richtet kein Subgrid ein. Unterstützt der Browser `subgrid`, übernehmen die Karten diese Zeilen, und Überschriften, Texte und Fußbereiche benachbarter Karten stehen auf gleicher Höhe. Ohne Unterstützung bleibt das einfache Layout erhalten.
