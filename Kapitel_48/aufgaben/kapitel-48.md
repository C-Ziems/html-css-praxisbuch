# Aufgaben und Lösungsvorschläge zu Kapitel 48: Nutzerpräferenzen und robuste Darstellung

## Aufgabe 1

**Aufgabe:** Die Tokens `--farbe-hinweis-hintergrund: #fff8db` und `--farbe-hinweis-text: #5c4400` gelten für das helle Schema. Lege passende Werte für das dunkle Schema fest, einmal mit einer Media Query und einmal mit `light-dark()`.

**Lösungsvorschlag**

Mit einer Media Query:

```css
:root {
    --farbe-hinweis-hintergrund: #fff8db;
    --farbe-hinweis-text: #5c4400;
}

@media (prefers-color-scheme: dark) {
    :root {
        --farbe-hinweis-hintergrund: #3a3000;
        --farbe-hinweis-text: #ffe9a6;
    }
}
```

Mit `light-dark()`:

```css
:root {
    color-scheme: light dark;
    --farbe-hinweis-hintergrund: light-dark(#fff8db, #3a3000);
    --farbe-hinweis-text: light-dark(#5c4400, #ffe9a6);
}
```

`light-dark()` setzt voraus, dass `color-scheme` beide Schemata erlaubt. Die dunklen Werte sind Beispiele; andere sind ebenso richtig, wenn der Kontrast in beiden Schemata ausreicht. Wir messen ihn mit den DevTools.

## Aufgabe 2

**Aufgabe:** Ein System verwendet `forced-colors: active`. Erkläre, warum wir dann keine eigenen Farben erzwingen und welche Gestaltung trotzdem erhalten bleiben sollte.

**Lösungsvorschlag**

Erzwungene Farben ersetzen unsere Farben durch eine Palette, die Nutzer für ihre Lesbarkeit gewählt haben. Würden wir eigene Farben erzwingen, nähmen wir ihnen diese Anpassung. Erhalten bleiben sollten Grenzen und Zustände, die nicht nur über Hintergrund oder Schatten vermittelt werden: Rahmen um Karten und Felder, sichtbare Fokuskonturen und Texte, die einen Zustand benennen.
