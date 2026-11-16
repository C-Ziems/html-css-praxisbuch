# Aufgaben und Lösungsvorschläge zu Kapitel 57: Eine Druckdarstellung ergänzen

## Aufgabe 1

**Aufgabe:** Im Ausdruck sollen Links auf andere Websites ihre Adresse in Klammern hinter dem Linktext zeigen. Schreibe die Regel für das Druckmodul.

**Lösungsvorschlag**

In `css/druck.css`:

```css
a[href^="http"]::after {
    content: " (" attr(href) ")";
    overflow-wrap: anywhere;
}
```

Auf Papier lassen sich Links nicht anklicken; die Adresse macht das Ziel trotzdem nachvollziehbar. Relative Links innerhalb unserer Website erfasst der Selektor nicht. Lange Adressen dürfen umbrechen.

## Aufgabe 2

**Aufgabe:** Im Ausdruck soll eine Tabelle möglichst nicht über einen Seitenumbruch geteilt werden, und jede `h2` soll auf einer neuen Seite beginnen. Schreibe die Regeln und erkläre, warum das Ergebnis nicht garantiert ist.

**Lösungsvorschlag**

```css
table {
    break-inside: avoid;
}

h2 {
    break-before: page;
}
```

Umbruchangaben sind Bitten an den Browser. Ist eine Tabelle höher als eine Seite, muss sie trotzdem geteilt werden. Browser setzen die Angaben außerdem unterschiedlich vollständig um. Das Ergebnis prüfen wir in der Druckvorschau.
