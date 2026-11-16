# Aufgaben und Lösungsvorschläge zu Kapitel 29: Responsive Bilder

## Aufgabe 1

**Aufgabe:** Ein Bild erscheint auf schmalen Bildschirmen in voller Viewportbreite, sonst in einer höchstens 40rem breiten Spalte. Es liegt in den Breiten 400, 800 und 1600 Pixel vor. Schreibe `srcset` und `sizes` dafür.

**Lösungsvorschlag**

```html
<img src="bilder/garten-800.jpg"
     srcset="bilder/garten-400.jpg 400w,
             bilder/garten-800.jpg 800w,
             bilder/garten-1600.jpg 1600w"
     sizes="(min-width: 40rem) 40rem, 100vw"
     alt="…" width="1600" height="1067">
```

Die Breitendeskriptoren nennen die tatsächliche Pixelbreite jeder Datei. `sizes` beschreibt die erwartete Darstellungsbreite: ab einer Viewportbreite von 40rem höchstens 40rem, darunter die volle Viewportbreite. Ziehen Innenabstände des Seitenrahmens noch Platz ab, kann die Bedingung entsprechend angepasst werden. Aus diesen Angaben und der Pixeldichte wählt der Browser eine Datei.

## Aufgabe 2

**Aufgabe:** Für ein Foto liegen zwei unterschiedlich zugeschnittene Dateien vor: eine breite Aufnahme für große Ansichten und ein quadratischer Ausschnitt mit dem wichtigsten Motiv für schmale Ansichten. Erkläre, warum `srcset` allein diese Auswahl nicht beschreibt, und skizziere eine Lösung mit `picture`.

**Lösungsvorschlag**

`srcset` mit Breitenangaben beschreibt Varianten desselben Motivs in verschiedenen Auflösungen. Der Browser darf daraus frei wählen, etwa nach Pixeldichte oder Datenvolumen. Ein anderer Bildausschnitt ist dagegen eine gestalterische Entscheidung, die wir dem Browser verbindlich vorgeben müssen. Dafür brauchen wir `picture` mit einer `source` und einer Medienbedingung:

```html
<picture>
    <source media="(max-width: 30rem)"
            srcset="bilder/haus-quadrat-600.jpg"
            width="600" height="600">
    <img src="bilder/haus-quer-1200.jpg" alt="Außenansicht unseres Hauses"
         width="1200" height="800">
</picture>
```

Das `img` trägt den Alternativtext für alle Varianten. Beide Ausschnitte müssen dieselbe Bildaussage vermitteln.

Mit `object-fit` und `object-position` aus Kapitel 28 könnten wir die breite Aufnahme zwar ebenfalls quadratisch zuschneiden. Der Browser lädt dann aber die ganze breite Datei, und der Ausschnitt ist nur so gut wie die gewählte Position. Eine eigens vorbereitete Datei zeigt das Motiv gezielt und spart auf schmalen Geräten Daten.
