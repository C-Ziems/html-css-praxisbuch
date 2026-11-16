# Aufgaben und Lösungsvorschläge zu Kapitel 17: Farben und Hintergründe

## Aufgabe 1

**Aufgabe:** Die Farbe `navy` soll in verschiedenen Schreibweisen vorliegen. Schreibe sie als Hexadezimalwert, mit `rgb()` und mit `hsl()`.

**Lösungsvorschlag**

```css
color: #000080;
color: rgb(0 0 128);
color: hsl(240 100% 25%);
```

Der `hsl()`-Wert ist gerundet; genau entspricht `navy` einer Helligkeit von etwa 25,1 %.

## Aufgabe 2

**Aufgabe:** Ein Hinweis erhält einmal `background-color: rgb(255 255 0 / 0.5);` und einmal `background-color: yellow; opacity: 0.5;`. Vergleiche beide Regeln und erkläre, warum der Text im zweiten Fall blasser erscheint.

**Lösungsvorschlag**

Im ersten Fall ist nur die Hintergrundfarbe halb durchsichtig. Der Text behält seine volle Deckkraft. `opacity: 0.5` wirkt dagegen auf das ganze Element einschließlich Text, Rahmen und Kindelementen. Deshalb erscheint der Text im zweiten Fall blasser und hat weniger Kontrast.
