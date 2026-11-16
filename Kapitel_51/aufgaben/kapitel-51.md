# Aufgaben und Lösungsvorschläge zu Kapitel 51: Scrollverhalten und Bedienkomfort

## Aufgabe 1

**Aufgabe:** Eine Seite besitzt einen fixierten, 4rem hohen Kopfbereich. Setze die Sprungziele so ab, dass ihre Überschriften nicht verdeckt werden.

**Lösungsvorschlag**

```css
html {
    scroll-padding-block-start: 5rem;
}
```

`scroll-padding` am Scrollcontainer, hier dem Wurzelelement, gilt für alle Sprungziele. Die 5rem decken den 4rem hohen Kopfbereich und einen kleinen Abstand ab. Alternativ erhält jedes Ziel `scroll-margin-block-start`.

## Aufgabe 2

**Aufgabe:** Eine horizontal scrollbare Bildleiste soll an jedem Bild einrasten. Schreibe die Regeln.

**Lösungsvorschlag**

```css
.bildleiste {
    display: flex;
    gap: 1rem;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    overscroll-behavior-x: contain;
}

.bildleiste > img {
    flex: 0 0 auto;
    scroll-snap-align: start;
}
```

`mandatory` rastet immer an einem Bild ein, `proximity` nur in dessen Nähe. `overscroll-behavior-x` verhindert, dass die Scrollbewegung am Ende der Leiste an die Seite weitergegeben wird.
