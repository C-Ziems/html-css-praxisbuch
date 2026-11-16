# Aufgaben und Lösungsvorschläge zu Kapitel 34: Tabellen vertiefen, Messwerte und Fortschritt darstellen

## Aufgabe 1

**Aufgabe:** Eine Tabelle besitzt die Zeilen „Wohnzimmer“ und „Küche“. Im Kopf sollen „Temperatur“ und „Luftfeuchte“ jeweils die Spalten „Tag“ und „Nacht“ überspannen. Schreibe den zweistufigen Kopf.

**Lösungsvorschlag**

```html
<table>
    <caption>Raumklima</caption>
    <colgroup><col></colgroup>
    <colgroup span="2"></colgroup>
    <colgroup span="2"></colgroup>
    <thead>
        <tr>
            <th rowspan="2" scope="col">Raum</th>
            <th colspan="2" scope="colgroup">Temperatur</th>
            <th colspan="2" scope="colgroup">Luftfeuchte</th>
        </tr>
        <tr>
            <th scope="col">Tag</th>
            <th scope="col">Nacht</th>
            <th scope="col">Tag</th>
            <th scope="col">Nacht</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Wohnzimmer</th>
            <td>21&nbsp;°C</td>
            <td>18&nbsp;°C</td>
            <td>45&nbsp;%</td>
            <td>50&nbsp;%</td>
        </tr>
        <tr>
            <th scope="row">Küche</th>
            <td>20&nbsp;°C</td>
            <td>17&nbsp;°C</td>
            <td>55&nbsp;%</td>
            <td>60&nbsp;%</td>
        </tr>
    </tbody>
</table>
```

Die Spaltengruppen fassen die beiden Tag- und Nachtspalten zusammen. `scope="colgroup"` ordnet „Temperatur“ und „Luftfeuchte“ ihrer jeweiligen Gruppe zu. Die Zelle „Raum“ überspannt mit `rowspan="2"` beide Kopfzeilen.

## Aufgabe 2

**Aufgabe:** Eine Seite zeigt folgende Angaben: a) den Ladestand des Hausspeichers von 70 %, b) den Fortschritt eines Firmware-Updates, c) eine Luftfeuchte von 55 % auf einer Skala von 0 bis 100 % mit einem günstigen Bereich von 40 bis 60 %, d) einen Download unbekannter Größe. Wähle für jede Angabe `meter` oder `progress` und gib für c) die vollständigen Attribute an.

**Lösungsvorschlag**

a) `meter`: ein Messwert in einem bekannten Bereich

b) `progress`: der Stand einer Aufgabe

c) `meter`:

```html
<meter min="0" max="100" low="40" high="60" optimum="50" value="55">55&nbsp;%</meter>
```

d) `progress` ohne `value`: ein unbestimmter Fortschritt

Zu jeder grafischen Anzeige gehört eine Beschriftung und ein sichtbarer Zahlenwert.
