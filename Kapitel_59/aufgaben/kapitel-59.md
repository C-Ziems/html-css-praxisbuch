# Aufgaben und Lösungsvorschläge zu Kapitel 59: Barrierefreiheit im Zusammenspiel prüfen

## Aufgabe 1

**Aufgabe:** Eine Seite enthält folgende Bedienelemente: a) `<button>X</button>` zum Schließen eines Hinweises, b) `<a href="geraete.html">Mehr</a>`, c) ein Suchfeld `<input type="search" name="q">` ohne Beschriftung. Beurteile ihre Namen und verbessere sie.

**Lösungsvorschlag**

a) „X“ wird als Buchstabe vorgelesen und sagt nichts über die Aufgabe. Besser ist ein sichtbarer Text oder zumindest ein zugänglicher Name:

```html
<button type="button">Hinweis schließen</button>
<!-- oder bei einem Symbol: -->
<button type="button" aria-label="Hinweis schließen">×</button>
```

b) „Mehr“ nennt kein Ziel. Besser: `<a href="geraete.html">Alle Gerätesteckbriefe</a>`.

c) Ein Feld ohne Beschriftung hat keinen verständlichen Namen:

```html
<label for="suche">Geräte durchsuchen</label>
<input type="search" id="suche" name="q">
```

## Aufgabe 2

**Aufgabe:** Die Einkaufsliste soll mit der Tastatur geprüft werden. Formuliere dafür eine Prüfnotiz mit Seite, Einstellung, Schritten, Erwartung, Beobachtung und Ergebnis.

**Lösungsvorschlag**

| Angabe | Eintrag |
|---|---|
| Seite | `einkaufsliste.html` über Live Server |
| Einstellung | Browser und Version, Standardzoom, nur Tastatur |
| Schritte | Seite laden, mit Tab durch alle Bedienelemente, Formular ohne Artikel absenden, gültige Werte eintragen und absenden |
| Erwartung | Sichtbarer Fokus in sinnvoller Reihenfolge, Fehlermeldung beim leeren Pflichtfeld, Übermittlung mit gültigen Werten |
| Beobachtung | Tatsächliches Verhalten, etwa „Fokus nach dem Absenden am Seitenanfang“ |
| Ergebnis | Bestanden, Fehler gefunden oder nicht geprüft |
