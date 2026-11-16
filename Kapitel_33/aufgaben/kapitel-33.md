# Aufgaben und Lösungsvorschläge zu Kapitel 33: Grundlagen von HTML-Tabellen

## Aufgabe 1

**Aufgabe:** Eine Tabelle soll den Stromverbrauch von drei Geräten in zwei Monaten zeigen. Lege sie mit Beschriftung sowie Spalten- und Zeilenüberschriften mit passendem `scope` an.

**Lösungsvorschlag**

```html
<table>
    <caption>Stromverbrauch in kWh</caption>
    <thead>
        <tr>
            <th scope="col">Gerät</th>
            <th scope="col">Oktober</th>
            <th scope="col">November</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Kühlschrank</th>
            <td>28</td>
            <td>27</td>
        </tr>
        <tr>
            <th scope="row">Waschmaschine</th>
            <td>15</td>
            <td>17</td>
        </tr>
        <tr>
            <th scope="row">Heizkörperthermostat</th>
            <td>1</td>
            <td>1</td>
        </tr>
    </tbody>
</table>
```

`caption` benennt die Tabelle und nennt die Einheit. Die Gerätenamen sind Zeilenüberschriften (`scope="row"`), die Monate Spaltenüberschriften (`scope="col"`).

## Aufgabe 2

**Aufgabe:** Ein zweispaltiges Seitenlayout aus Text und Abbildung wird mit `table` gebaut. Erkläre, warum wir das nicht tun und was ein Screenreader in diesem Fall ankündigt.

**Lösungsvorschlag**

Eine Tabelle beschreibt Daten, deren Bedeutung von Zeile und Spalte abhängt. Text und Abbildung stehen in keiner solchen Beziehung. Ein Screenreader kann trotzdem eine Tabelle mit Zeilen und Spalten ankündigen und die Navigation von Zelle zu Zelle anbieten. Manche Screenreader versuchen, Layouttabellen zu erkennen; darauf können wir uns nicht verlassen. Die Ankündigung führt in die Irre. Außerdem passt sich ein Tabellenlayout schlecht an schmale Bildschirme an. Für das Layout verwenden wir Grid oder Flexbox.
