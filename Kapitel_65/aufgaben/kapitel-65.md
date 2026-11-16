# Aufgaben und Lösungsvorschläge zu Kapitel 65: Das Smart Home weiterentwickeln

## Aufgabe 1

**Aufgabe:** Das Smart Home soll um die Funktion „Raumtemperaturen von Hand eintragen und auf allen Geräten sehen“ erweitert werden. Plane die Erweiterung stichpunktartig in den sechs Schritten aus Abschnitt 65.2.

**Lösungsvorschlag**

1. Aufgabe: Bewohner tragen Temperaturen ein und sehen sie auf allen Geräten.
2. Datenflüsse: Eingaben gehen an einen Server und werden in einer Datenbank gespeichert; wer darf lesen und schreiben, wie lange werden Daten aufbewahrt, welche Informationen brauchen Betroffene (Kapitel 61)?
3. HTML-Grundlage: ein Formular mit Raum (`select`) und Temperatur (`input type="number"` mit Grenzen) sowie eine Tabelle der gespeicherten Werte.
4. Darstellung: vorhandene Formular- und Tabellenregeln nutzen, neue Regeln in `komponenten`.
5. Verhalten: Serveranwendung prüft und speichert die Werte, eine Anmeldung schützt den Zugriff; optional aktualisiert JavaScript die Tabelle ohne Neuladen.
6. Prüfen: Tastatur, Screenreader, Fehlermeldungen, schmale Ansicht, Druck, Validierung, Verhalten bei Serverfehlern.

## Aufgabe 2

**Aufgabe:** Ein Branch `farbschema-schalter` soll angelegt werden. Zwischendurch wird auf `main` ein Fehler behoben, später wird der Branch zusammengeführt. Gib die Git-Befehle an und erkläre, was zu tun ist, wenn Git den Wechsel auf `main` verweigert.

**Lösungsvorschlag**

```
git switch -c farbschema-schalter
# … ändern, prüfen, committen …
git status
git switch main
# … Fehler beheben, prüfen, committen …
git switch farbschema-schalter
# … weiterarbeiten …
git switch main
git merge farbschema-schalter
```

Verweigert Git den Wechsel, würden nicht committete Änderungen überschrieben. Wir committen sie zuerst, wenn sie fertig sind, oder machen sie rückgängig, wenn sie verworfen werden sollen. Danach zeigt `git status` einen sauberen Arbeitsstand, und der Wechsel gelingt.
