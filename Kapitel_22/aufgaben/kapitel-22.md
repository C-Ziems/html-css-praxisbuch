# Aufgaben und Lösungsvorschläge zu Kapitel 22: Textumfluss mit float, clear und shape-outside

## Aufgabe 1

**Aufgabe:** Ein Absatz soll mit einem großen Anfangsbuchstaben beginnen, den der Text umfließt, und der umgebende Container soll ihn vollständig umschließen. Gestalte den Buchstaben als `span` mit der Klasse `initiale`.

**Lösungsvorschlag**

```html
<div class="artikeltext">
    <p><span class="initiale">D</span>as Haus wurde 2024 vernetzt …</p>
</div>
```

```css
.artikeltext {
    display: flow-root;
}

.initiale {
    float: inline-start;
    font-size: 3em;
    line-height: 1;
    margin-inline-end: 0.25rem;
}
```

`float` lässt den Text um den Buchstaben fließen. `display: flow-root` gibt dem Container einen eigenen Blockformatierungskontext, sodass er den Float in seine Höhe einbezieht, auch wenn der Absatz kurz ist.

## Aufgabe 2

**Aufgabe:** Eine Navigation soll ihre Links nebeneinander anordnen. Erkläre, warum wir dafür nicht `float`, sondern Flexbox verwenden.

**Lösungsvorschlag**

`float` ist für Textumfluss gedacht. Eine Navigation mit Floats braucht zusätzliche Regeln zum Umschließen und bietet keine einfache Steuerung von Abständen, Umbruch und Ausrichtung. Flexbox ordnet die Einträge entlang einer Achse an, verteilt Zwischenräume mit `gap`, bricht mit `flex-wrap` um und richtet die Einträge aneinander aus.
