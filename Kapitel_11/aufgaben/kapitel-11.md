# Aufgaben und Lösungsvorschläge zu Kapitel 11: Mehrseitige Website, Pfade und Projektstruktur

## Aufgabe 1

**Aufgabe:** Eine Website besitzt die folgende Ordnerstruktur. Bestimme die relativen Pfade a) von `index.html` zu `thermostat.html`, b) von `thermostat.html` zu `kontakt.html`, c) von `faq.html` zu `thermostat.png`, d) von `thermostat.html` zum Abschnitt `#batterie` in `faq.html`.

```text
website/
├── index.html
├── kontakt.html
├── geraete/
│   ├── thermostat.html
│   └── bilder/
│       └── thermostat.png
└── hilfe/
    └── faq.html
```

**Lösungsvorschlag**

a) `geraete/thermostat.html`

b) `../kontakt.html`

c) `../geraete/bilder/thermostat.png`

d) `../hilfe/faq.html#batterie`

Ausgangspunkt ist jeweils der Ordner der Datei, in der der Verweis steht. `../` wechselt eine Ebene nach oben.

## Aufgabe 2

**Aufgabe:** Eine Seite liegt unter `https://example.com/smart-home/index.html`. Ihr Link `<a href="/haus.html">Unser Haus</a>` führt nicht zur Hausseite. Erkläre die Ursache und gib eine Korrektur an.

**Lösungsvorschlag**

Der führende Schrägstrich beginnt an der Wurzel des Ursprungs. Der Link führt deshalb zu `https://example.com/haus.html`; der Ordner `smart-home` fehlt im Ziel. Die Korrektur ist ein dokumentrelativer Verweis:

```html
<a href="haus.html">Unser Haus</a>
```

Auch `/smart-home/haus.html` führt zum Ziel. Dieser Pfad setzt aber voraus, dass die Website immer im Ordner `smart-home` liegt; der dokumentrelative Verweis funktioniert auch nach einem Umzug in einen anderen Ordner.
