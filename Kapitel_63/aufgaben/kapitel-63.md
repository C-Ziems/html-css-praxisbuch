# Aufgaben und Lösungsvorschläge zu Kapitel 63: Den Projektstand mit Git verwalten

## Aufgabe 1

**Aufgabe:** Nach einer Änderung an `css/druck.css` soll nur diese Datei aufgezeichnet werden. Gib die Befehle in sinnvoller Reihenfolge an, einschließlich der Prüfung vor und nach dem Commit.

**Lösungsvorschlag**

```
git status
git diff css/druck.css
git add css/druck.css
git diff --staged
git commit -m "Druckregeln für Tabellen verbessern"
git status
git log --oneline
```

`git status` zeigt zuerst, welche Dateien geändert sind. `git diff` zeigt die Änderung, `git diff --staged` die vorgemerkte Auswahl. Nach dem Commit bestätigen `git status` und `git log --oneline` den Stand. Die Nachricht benennt die tatsächliche Aufgabe.

## Aufgabe 2

**Aufgabe:** Eine Datei wird geändert und mit `git add` vorgemerkt, danach erneut geändert, und anschließend folgt `git commit`. Erkläre, welcher Stand im Commit landet.

**Lösungsvorschlag**

Im Commit landet der Stand zum Zeitpunkt von `git add`. Die zweite Änderung ist nicht vorgemerkt und bleibt im Arbeitsverzeichnis. `git status` zeigt die Datei deshalb danach weiterhin als geändert an. Soll auch die zweite Änderung in den Commit, merken wir die Datei vor dem Commit erneut mit `git add` vor.
