# Aufgaben und Lösungsvorschläge zu Kapitel 9: Listen und Beschreibungslisten

## Aufgabe 1

**Aufgabe:** Eine Seite enthält folgende Inhalte: a) die Zutaten eines Rezepts, b) die Schritte eines Batteriewechsels, c) Geräte mit ihrem Batterietyp, d) eine Rangliste der drei Geräte mit dem höchsten Verbrauch, absteigend sortiert. Wähle für jeden Inhalt `ul`, `ol` oder `dl` und begründe deine Wahl: Prüfe bei `ul` und `ol`, ob das Vertauschen der Einträge die Aussage verändert, und bei `dl`, welche Namen und Werte einander zugeordnet sind.

**Lösungsvorschlag**

a) `ul`: Werden die Zutaten vertauscht, ändert sich die Aussage nicht.

b) `ol`: Die Schritte müssen in dieser Reihenfolge ausgeführt werden; ein Vertauschen ändert die Anleitung.

c) `dl`: Hier hilft nicht die Vertauschprobe, sondern die Zuordnung: Jedem Gerät (`dt`) wird ein Wert, der Batterietyp (`dd`), zugeordnet.

d) `ol`: Die absteigende Rangfolge ist Teil der Information; ein Vertauschen würde die Aussage verfälschen.

## Aufgabe 2

**Aufgabe:** Die folgende Verschachtelung enthält einen Fehler. Finde ihn und korrigiere den Ausschnitt:

```html
<ul>
    <li>Erdgeschoss</li>
    <ul>
        <li>Wohnzimmer</li>
        <li>Küche</li>
    </ul>
    <li>Obergeschoss</li>
</ul>
```

**Lösungsvorschlag**

Die Unterliste steht zwischen zwei Listeneinträgen. Sie gehört in den Eintrag, den sie näher beschreibt:

```html
<ul>
    <li>Erdgeschoss
        <ul>
            <li>Wohnzimmer</li>
            <li>Küche</li>
        </ul>
    </li>
    <li>Obergeschoss</li>
</ul>
```
