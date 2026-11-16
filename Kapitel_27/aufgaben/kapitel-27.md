# Aufgaben und Lösungsvorschläge zu Kapitel 27: Logische Eigenschaften und Schreibrichtungen

## Aufgabe 1

**Aufgabe:** Für horizontalen Text von links nach rechts enthält eine Regel die physischen Angaben `margin-left: 1rem; padding-top: 0.5rem; width: 20rem; right: 0;`. Schreibe sie so mit logischen Eigenschaften, dass die Darstellung gleich bleibt.

**Lösungsvorschlag**

```css
margin-inline-start: 1rem;
padding-block-start: 0.5rem;
inline-size: 20rem;
inset-inline-end: 0;
```

Diese Zuordnung gilt für horizontalen Text von links nach rechts. Bei `dir="rtl"` liegt der Zeilenanfang rechts, in einem vertikalen Schreibmodus verlaufen Inline- und Blockachse senkrecht beziehungsweise waagerecht. Die logischen Angaben folgen dann jeweils der neuen Richtung.

## Aufgabe 2

**Aufgabe:** Eine Karte besitzt `padding-inline-start: 2rem`. Erkläre, was sich ändert, wenn das Dokument `dir="rtl"` erhält.

**Lösungsvorschlag**

In einem Dokument mit `dir="rtl"` beginnt die Inline-Achse rechts. `padding-inline-start` setzt den Innenabstand deshalb an die rechte Seite der Karte, also wieder an den Zeilenanfang. Ein physisches `padding-left` bliebe dagegen links und läge damit am Zeilenende.
