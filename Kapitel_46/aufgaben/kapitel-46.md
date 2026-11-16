# Aufgaben und Lösungsvorschläge zu Kapitel 46: Media Queries und inhaltsbasierte Breakpoints

## Aufgabe 1

**Aufgabe:** Eine Bildergalerie soll einspaltig beginnen und ab 40rem Viewportbreite zwei, ab 64rem drei Spalten zeigen. Schreibe die Regeln in Bereichsschreibweise.

**Lösungsvorschlag**

```css
.galerie {
    display: grid;
    gap: 1rem;
}

@media (width >= 40rem) {
    .galerie {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (width >= 64rem) {
    .galerie {
        grid-template-columns: repeat(3, 1fr);
    }
}
```

Die Grundregel ist einspaltig. Die Abfragen ergänzen weitere Spalten, sobald der Platz reicht. Die Grenzen sollten aus dem Inhalt abgeleitet werden: Wir prüfen mit stufenlos veränderter Breite, ab wann zwei oder drei Bilder nebeneinander gut wirken.

## Aufgabe 2

**Aufgabe:** Schaltflächen sollen nur dann größere Innenabstände erhalten, wenn das wichtigste Zeigegerät ungenau ist, etwa ein Finger. Schreibe die Abfrage.

**Lösungsvorschlag**

```css
@media (pointer: coarse) {
    button {
        padding: 0.75rem 1.25rem;
    }
}
```

`pointer` beschreibt das wichtigste Zeigegerät. `coarse` steht für eine ungenaue Eingabe wie einen Finger. Soll die Regel greifen, sobald irgendein ungenaues Zeigegerät vorhanden ist, verwenden wir `any-pointer`.
