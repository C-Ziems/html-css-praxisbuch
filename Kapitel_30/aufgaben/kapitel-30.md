# Aufgaben und Lösungsvorschläge zu Kapitel 30: Image Maps und grafische Navigation

## Aufgabe 1

**Aufgabe:** Ein Bild mit 600 × 400 Pixeln soll zwei Linkflächen erhalten: ein Rechteck von (0, 0) bis (300, 200) zur Küche und einen Kreis um (450, 300) mit dem Radius 80 zum Bad. Schreibe die Image Map.

**Lösungsvorschlag**

```html
<img src="bilder/plan.png" alt="Grundriss mit Küche und Bad"
     width="600" height="400" usemap="#plan">
<map name="plan">
    <area shape="rect" coords="0,0,300,200" href="#kueche" alt="Küche">
    <area shape="circle" coords="450,300,80" href="#bad" alt="Bad">
</map>
```

Beim Rechteck stehen die Koordinaten der linken oberen und der rechten unteren Ecke, beim Kreis Mittelpunkt und Radius. Jede Linkfläche erhält einen eigenen Alternativtext.

## Aufgabe 2

**Aufgabe:** CSS verkleinert das Bild aus Aufgabe 1 auf halbe Breite. Erkläre, warum die Linkflächen nicht mehr passen, und welche Ergänzung die Bedienung trotzdem sicherstellt.

**Lösungsvorschlag**

Die Koordinaten skalieren nicht mit der Darstellung. Bei halber Breite ist das Bild nur noch 300 Pixel breit, der Kreis um (450, 300) liegt dann außerhalb, und das Rechteck deckt das ganze Bild ab. Sichtbare Textlinks zu denselben Zielen stellen sicher, dass alle Bereiche erreichbar bleiben, unabhängig von der Bildgröße.
