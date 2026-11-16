# Aufgaben und Lösungsvorschläge zu Kapitel 28: Bilder und Bildunterschriften

## Aufgabe 1

**Aufgabe:** Eine Seite enthält drei Bilder: a) ein Foto des Thermostats in einem Gerätesteckbrief, b) eine dekorative Wellenlinie zwischen zwei Abschnitten, c) ein Logo, das als Link zur Startseite dient. Lege für jedes Bild den Alternativtext fest und begründe ihn.

**Lösungsvorschlag**

a) `alt="Heizkörperthermostat mit Drehregler und Display"` – Das Foto zeigt, wie das Gerät aussieht. Der Text beschreibt, was für den Steckbrief wichtig ist.

b) `alt=""` – Die Linie ist rein dekorativ. Ein leerer Alternativtext sorgt dafür, dass Screenreader sie übergehen.

c) `alt="Startseite"` oder `alt="Mein Smart Home – Startseite"` – Bei einem Bildlink beschreibt der Alternativtext das Linkziel, nicht das Aussehen des Logos.

Die Formulierungen sind Beispiele. Entscheidend ist, welche Aufgabe das Bild an seiner Stelle erfüllt.

## Aufgabe 2

**Aufgabe:** Das Foto ist 400 × 300 Pixel groß und zeigt die Vorderseite eines weißen Heizkörperthermostats in einem Gerätesteckbrief. Die folgende Zeile lässt sich an drei Stellen verbessern. Finde die Verbesserungen und schreibe eine korrigierte Fassung:

```html
<img src="bilder/thermostat.jpg" alt="Bild von einem Thermostat" width="400px">
```

**Lösungsvorschlag**

```html
<img src="bilder/thermostat.jpg" alt="Vorderseite des weißen Heizkörperthermostats"
     width="400" height="300">
```

1. „Bild von“ ist überflüssig, denn Screenreader kündigen das Bild bereits an. Der neue Text nennt, was das Foto im Steckbrief zeigt.
2. `width` erwartet eine Zahl ohne Einheit.
3. `height` fehlt. Mit beiden Angaben kennt der Browser das Seitenverhältnis und reserviert vor dem Laden den passenden Platz. Die Werte entsprechen den tatsächlichen Abmessungen der Datei, hier 400 × 300 Pixel.
