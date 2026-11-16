# Aufgaben und Lösungsvorschläge zu Kapitel 41: Custom Properties, @property und Design Tokens

## Aufgabe 1

**Aufgabe:** Eine Komponente `.karte` soll die Tokens `--karte-abstand` und `--karte-hintergrund` verwenden. In der Variante `.karte.hervorgehoben` wird nur der Hintergrund überschrieben. Lege die Tokens fest und verwende sie.

**Lösungsvorschlag**

```css
.karte {
    --karte-abstand: var(--abstand-mittel);
    --karte-hintergrund: var(--farbe-hintergrund);
    padding: var(--karte-abstand);
    background-color: var(--karte-hintergrund);
}

.karte.hervorgehoben {
    --karte-hintergrund: var(--farbe-flaeche-abgesetzt);
}
```

Die Variante setzt nur den Token neu. Die Deklaration `background-color: var(--karte-hintergrund)` bleibt unverändert und verwendet am hervorgehobenen Element automatisch den neuen Wert.

## Aufgabe 2

**Aufgabe:** Eine Regel lautet `color: var(--textfarbe, black)`, und `--textfarbe` ist auf `20px` gesetzt. Erkläre, warum der Ersatzwert nicht greift und welche Farbe der Text stattdessen erhält.

**Lösungsvorschlag**

Der Ersatzwert in `var()` greift, wenn die Custom Property keinen verwendbaren Wert liefert, etwa weil sie fehlt oder zyklisch ist. Ob der Wert zur Eigenschaft passt, prüft er nicht. Hier ist `--textfarbe` gesetzt, `var()` setzt also `20px` ein. `color: 20px` ist ungültig, aber erst beim Berechnen des Wertes. Die Deklaration verhält sich dann wie `unset`: Weil `color` vererbt wird, erhält der Text die Farbe des Elternelements, nicht Schwarz. Eine zuvor überstimmte Deklaration lebt dabei nicht wieder auf.
