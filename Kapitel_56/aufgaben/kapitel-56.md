# Aufgaben und Lösungsvorschläge zu Kapitel 56: Templates, Shadow DOM und die Einbindung von Scripts

## Aufgabe 1

**Aufgabe:** Die Scriptdatei `js/start.js` soll das Einlesen des Dokuments nicht aufhalten und erst danach ausgeführt werden. Binde sie ein und schreibe einen passenden Hinweis für deaktiviertes Scripting.

**Lösungsvorschlag**

```html
<script src="js/start.js" defer></script>
<noscript>
    <p>Einige Zusatzfunktionen benötigen JavaScript. Alle Inhalte sind auch ohne sie verfügbar.</p>
</noscript>
```

`defer` lädt die Datei parallel zum Einlesen und führt sie danach aus, mehrere `defer`-Scripts in ihrer Reihenfolge. `async` würde die Ausführung starten, sobald die Datei geladen ist, ohne feste Reihenfolge. Der `noscript`-Hinweis erscheint nur bei deaktiviertem Scripting, nicht bei einem fehlgeschlagenen Script.

## Aufgabe 2

**Aufgabe:** Eine Komponente verwendet ein `slot`-Element. Erkläre, wann dessen eigener Inhalt angezeigt wird und wann ein Inhalt des Hosts.

**Lösungsvorschlag**

Ein `slot` zeigt Inhalte des Hosts an, die ihm zugeordnet sind, bei benannten Slots über das Attribut `slot`. Ist kein passender Inhalt vorhanden, erscheint der eigene Inhalt des `slot`-Elements als Ersatz.
