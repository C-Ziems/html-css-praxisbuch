# Aufgaben und Lösungsvorschläge zu Kapitel 24: CSS Grid: Flexible Raster aufbauen

## Aufgabe 1

**Aufgabe:** Eine Kartenübersicht soll so viele Spalten zeigen, wie passen, jeweils mindestens 12rem breit, mit 1rem Abstand. Schreibe `grid-template-columns` und erkläre, warum `min(12rem, 100%)` statt `12rem` steht.

**Lösungsvorschlag**

```css
.kartenuebersicht {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(min(12rem, 100%), 1fr));
    gap: 1rem;
}
```

Mit `minmax(12rem, 1fr)` wäre jede Spalte mindestens 12rem breit, auch wenn der Container schmaler ist. Die Karte würde dann über den Rand hinausragen. `min(12rem, 100%)` begrenzt die Untergrenze auf die verfügbare Breite.

## Aufgabe 2

**Aufgabe:** Eine Spalte enthält ein sehr langes Wort. Erkläre an diesem Beispiel den Unterschied zwischen `1fr 1fr` und `minmax(0, 1fr) minmax(0, 1fr)`.

**Lösungsvorschlag**

Eine `1fr`-Spur besitzt eine inhaltsabhängige Untergrenze: Sie wird nicht schmaler als ihr breitester nicht umbrechbarer Inhalt. Ein sehr langes Wort macht diese Spalte deshalb breiter, und die Spalten sind nicht mehr gleich breit. Mit `minmax(0, 1fr)` entfällt diese Untergrenze, beide Spalten bleiben gleich breit. Das lange Wort ragt dann jedoch über seine Spalte hinaus, wenn wir ihm keinen Umbruch erlauben, etwa mit `overflow-wrap: anywhere`.
