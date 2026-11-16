# Aufgaben und Lösungsvorschläge zu Kapitel 43: Rahmen, Konturen, Schatten und visuelle Details

## Aufgabe 1

**Aufgabe:** Eine Hinweisbox soll eine 4 Pixel starke Kante am Zeilenanfang, eine Rundung aus einem Token und einen dezenten Schatten erhalten. Gestalte die Box.

**Lösungsvorschlag**

```css
.hinweisbox {
    padding: var(--abstand-mittel);
    border: 1px solid var(--farbe-rahmen);
    border-inline-start-width: 4px;
    border-radius: var(--radius-standard);
    box-shadow: var(--schatten-karte);
}
```

`border-inline-start-width` setzt die verstärkte Kante an den Zeilenanfang, auch bei anderer Schreibrichtung. Rundung und Schatten verwenden die vorhandenen Tokens.

## Aufgabe 2

**Aufgabe:** Ein Stylesheet zeigt den Fokus mit `outline`. Erkläre, warum wir dafür nicht `border` verwenden und warum `outline: none` ohne Ersatz ein Problem ist.

**Lösungsvorschlag**

Ein Rahmen gehört zur Box und beansprucht Platz. Erscheint er erst beim Fokus, wird das Element größer, und benachbarte Inhalte verschieben sich. `outline` zeichnet eine Kontur ohne Platzbedarf, die Anordnung bleibt stabil. `outline: none` ohne andere sichtbare Kennzeichnung nimmt Menschen, die mit der Tastatur arbeiten, die Information, welches Element gerade bedient wird.
