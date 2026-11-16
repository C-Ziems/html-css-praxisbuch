# Aufgaben und Lösungsvorschläge zu Kapitel 36: Input-Typen und Eingabehilfen

## Aufgabe 1

**Aufgabe:** Ein Formular fragt a) eine E-Mail-Adresse, b) eine Postleitzahl, c) eine Raumtemperatur von 15 bis 25 °C in halben Grad und d) einen Liefertermin ab. Wähle für jede Angabe den Eingabetyp und hilfreiche Attribute.

**Lösungsvorschlag**

```html
<input type="email" id="email" name="email" autocomplete="email">
<input type="text" id="plz" name="plz" inputmode="numeric" autocomplete="postal-code">
<input type="number" id="temperatur" name="temperatur" min="15" max="25" step="0.5">
<input type="date" id="liefertermin" name="liefertermin">
```

Die Postleitzahl ist eine Ziffernfolge, keine Zahl, mit der gerechnet wird. Sie bleibt deshalb Text; `inputmode="numeric"` bietet trotzdem eine Zifferntastatur an. Zu jedem Feld gehört wie gewohnt ein `label`.

## Aufgabe 2

**Aufgabe:** Ein Formular fragt „Benachrichtigung per E-Mail und SMS“ und „Versandart Standard oder Express“ ab. Begründe, wann Checkboxen und wann Radiobuttons passen, und schreibe das HTML für die Versandart.

**Lösungsvorschlag**

Die Benachrichtigungen sind unabhängig voneinander: Man kann E-Mail, SMS, beides oder keines wählen. Dafür passen Checkboxen. Bei der Versandart ist genau eine Wahl möglich; dafür passen Radiobuttons mit demselben `name`:

```html
<fieldset>
    <legend>Versandart</legend>
    <label>
        <input type="radio" name="versand" value="standard" checked>
        Standard
    </label>
    <label>
        <input type="radio" name="versand" value="express">
        Express
    </label>
</fieldset>
```
