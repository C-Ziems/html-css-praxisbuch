# Aufgaben und Lösungsvorschläge zu Kapitel 13: Selektoren, Klassen und IDs

## Aufgabe 1

**Aufgabe:** Ein Stylesheet soll folgende Elemente auswählen: a) alle Links innerhalb der Hauptnavigation, b) nur die direkten Listeneinträge einer Liste mit der Klasse `geraeteliste`, c) Elemente, die zugleich die Klassen `pruefen` und `dringend` tragen, d) den Link mit `aria-current="page"`. Schreibe die passenden Selektoren.

**Lösungsvorschlag**

```css
.hauptnavigation a { }          /* a) */
.geraeteliste > li { }          /* b) */
.pruefen.dringend { }           /* c) */
[aria-current="page"] { }       /* d) */
```

Bei b) beschränkt der Kindkombinator `>` die Auswahl auf direkte Kinder; Einträge verschachtelter Listen bleiben ausgenommen. Bei c) steht kein Leerzeichen zwischen den Klassen, weil beide am selben Element gefordert sind.

## Aufgabe 2

**Aufgabe:** Für dringende Prüfungen wird der Klassenname `rot` vorgeschlagen. Begründe, warum dieser Name ungeeignet ist, und schlage einen besseren vor.

**Lösungsvorschlag**

`rot` beschreibt das Aussehen, nicht die Aufgabe. Ändert sich die Gestaltung, etwa zu Orange oder zu einer fetten Schrift, passt der Name nicht mehr, und HTML und CSS widersprechen sich. Besser ist ein Name, der den Zustand benennt, zum Beispiel `dringend`, wie in unserem Projekt.
