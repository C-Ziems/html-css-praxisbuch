# Aufgaben und Lösungsvorschläge zu Kapitel 14: CSS-Werte, Einheiten und grundlegende Funktionen

## Aufgabe 1

**Aufgabe:** Die Wurzelschriftgröße beträgt 16 Pixel. Bestimme die Ergebnisse in Pixeln für a) `font-size: 2rem`, b) `font-size: 1.5em` bei einer Elternschrift von 20 Pixeln, c) `line-height: 1.5` bei 18 Pixeln Schriftgröße, d) `width: calc(100% - 2rem)` in einem 600 Pixel breiten Container.

**Lösungsvorschlag**

a) 2 × 16 px = 32 px

b) 1,5 × 20 px = 30 px (in `font-size` bezieht sich `em` auf die Schrift des Elternelements)

c) 1,5 × 18 px = 27 px

d) 600 px − 32 px = 568 px

## Aufgabe 2

**Aufgabe:** Die Wurzelschriftgröße beträgt 16 Pixel. Eine Überschrift soll mit 5 Prozent der Viewportbreite wachsen, aber nie kleiner als `1.5rem` und nie größer als `2.5rem` werden. Schreibe die Regel und berechne den Wert bei einem 600 Pixel breiten Viewport.

**Lösungsvorschlag**

```css
h1 {
    font-size: clamp(1.5rem, 5vw, 2.5rem);
}
```

Bei 600 px Viewportbreite ergibt `5vw` 30 px. Der Wert liegt zwischen 24 px (`1.5rem`) und 40 px (`2.5rem`), die Schriftgröße beträgt deshalb 30 px.
