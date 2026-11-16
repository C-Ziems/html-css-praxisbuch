# Aufgaben und Lösungsvorschläge zu Kapitel 26: Mehrspaltensatz und Layoutentscheidungen

## Aufgabe 1

**Aufgabe:** Eine Seite enthält a) einen längeren Einleitungstext, b) eine Reihe von Schaltflächen, c) gleichartige Produktkarten, deren Spalten aneinander ausgerichtet sind. Wähle für jeden Inhalt das passende Layoutverfahren und begründe deine Wahl.

**Lösungsvorschlag**

a) Mehrspaltensatz: Ein zusammenhängender Text fließt durch Spalten, sofern er überschaubar bleibt und die Spalten nicht zu lang werden.

b) Flexbox: Die Schaltflächen stehen in einer Reihe entlang einer Achse und dürfen umbrechen.

c) Grid: Zeilen und Spalten sind gemeinsam ausgerichtet; mit Subgrid können auch die Inhalte der Karten an gemeinsamen Linien beginnen.

Andere Entscheidungen sind begründbar. Sollen die Schaltflächen etwa in gleich breiten Spalten stehen, passt auch Grid. Entscheidend ist, dass das Verfahren zur Art der Anordnung passt.

## Aufgabe 2

**Aufgabe:** In einem mehrspaltigen Text soll eine Zwischenüberschrift alle Spalten überspannen. Schreibe die Regel.

**Lösungsvorschlag**

```css
.hausbeschreibung h3 {
    column-span: all;
}
```

Die Überschrift überspannt alle Spalten, der Text davor und danach verteilt sich jeweils wieder auf die Spalten.
