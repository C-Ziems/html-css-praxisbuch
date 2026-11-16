# Aufgaben und Lösungsvorschläge zu Kapitel 12: CSS einbinden und die erste Gestaltung aufbauen

## Aufgabe 1

**Aufgabe:** In dem folgenden Stylesheet wirken zwei Angaben nicht. Finde die Ursachen und bestätige sie mit den DevTools:

```css
p {
    color: navy
    font-family: Arial, sans-serif;
}
h2 {
    colour: darkblue;
}
```

**Lösungsvorschlag**

1. Nach `color: navy` fehlt das Semikolon. Der Browser liest deshalb `navy font-family: Arial, sans-serif` als einen einzigen Wert für `color`. Dieser Wert ist ungültig, die gesamte Deklaration wird verworfen. Weder die Farbe noch die Schrift wirken.
2. `colour` ist keine CSS-Eigenschaft (CSS verwendet die amerikanische Schreibweise `color`). Die Deklaration wird verworfen.

In den DevTools erscheinen beide Deklarationen im Bereich Styles durchgestrichen und mit einem Warnsymbol. Korrigiert:

```css
p {
    color: navy;
    font-family: Arial, sans-serif;
}

h2 {
    color: darkblue;
}
```

## Aufgabe 2

**Aufgabe:** Ein Stylesheet setzt `color` und `background-color` an `body`. Erkläre, warum `color` alle Absätze einfärbt, `background-color` dagegen nicht vererbt wird, und warum die Absätze trotzdem auf dieser Hintergrundfarbe erscheinen.

**Lösungsvorschlag**

`color` ist eine vererbte Eigenschaft: Legt ein Absatz selbst keine Textfarbe fest, übernimmt er den Wert seines Elternelements. `background-color` wird nicht vererbt; der Anfangswert jedes Elements ist `transparent`. Die Absätze besitzen also keinen eigenen Hintergrund, und durch ihre durchsichtige Fläche ist der Hintergrund von `body` zu sehen. Das ist keine Vererbung, sondern Durchscheinen.
