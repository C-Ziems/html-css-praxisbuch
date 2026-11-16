# Aufgaben und Lösungsvorschläge zu Kapitel 45: Flexible Größen mit CSS-Einheiten und Funktionen

## Aufgabe 1

**Aufgabe:** Die Wurzelschriftgröße beträgt 16 Pixel. Eine Seitenleiste soll 30 % ihres Containers breit sein, mindestens 12rem und höchstens 20rem. Schreibe die Regel und berechne die Breite in einem 800 Pixel breiten Container.

**Lösungsvorschlag**

```css
.seitenleiste {
    inline-size: clamp(12rem, 30%, 20rem);
}
```

Bei 800 px Containerbreite ergibt 30 % 240 px. Die Grenzen liegen bei 192 px (`12rem`) und 320 px (`20rem`), die Seitenleiste ist deshalb 240 px breit.

## Aufgabe 2

**Aufgabe:** Eine Überschrift verwendet `font-size: 4vw` ohne `rem`-Anteil. Erkläre, warum das beim Zoomen problematisch ist.

**Lösungsvorschlag**

`vw` hängt nur von der Viewportbreite ab. Beim Zoomen wird die Viewportbreite in CSS-Pixeln kleiner, während jedes CSS-Pixel größer dargestellt wird. Beide Effekte heben sich auf, und die Schrift wächst nicht mit. Ein `rem`-Anteil, etwa in `clamp(1.5rem, 1rem + 2vw, 3rem)`, wächst beim Zoomen mit und sorgt dafür, dass Text vergrößert werden kann.
