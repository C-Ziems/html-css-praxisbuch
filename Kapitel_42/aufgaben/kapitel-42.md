# Aufgaben und Lösungsvorschläge zu Kapitel 42: Fortgeschrittene Typografie und Webfonts

## Aufgabe 1

**Aufgabe:** Eine lokal gespeicherte Schrift „Hausschrift“ liegt in zwei Dateien vor (Regular und Bold, WOFF2). Schreibe die `@font-face`-Regeln mit `font-display: swap` und gib eine Schriftfamilienliste mit Ersatzschriften an.

**Lösungsvorschlag**

```css
@font-face {
    font-family: "Hausschrift";
    src: url("../schriften/hausschrift-regular.woff2") format("woff2");
    font-weight: 400;
    font-style: normal;
    font-display: swap;
}

@font-face {
    font-family: "Hausschrift";
    src: url("../schriften/hausschrift-bold.woff2") format("woff2");
    font-weight: 700;
    font-style: normal;
    font-display: swap;
}

body {
    font-family: "Hausschrift", Arial, Helvetica, sans-serif;
}
```

Jede statische Schriftdatei erhält eine eigene Regel mit demselben Familiennamen. Der Pfad bezieht sich auf die Moduldatei im Ordner `css`, deshalb beginnt er mit `../`. Vor dem Einsatz prüfen wir die Nutzungsbedingungen der Schrift.

## Aufgabe 2

**Aufgabe:** Eine Webfont wird mit `font-display: swap` geladen. Erkläre, warum es zu einem kurzen Umspringen der Schrift kommen kann und wie eine passende Ersatzschrift das abmildert.

**Lösungsvorschlag**

Mit `swap` zeigt der Browser den Text sofort in einer Ersatzschrift und tauscht sie aus, sobald die Webfont geladen ist. Unterscheiden sich beide Schriften in Breite oder Höhe, verschieben sich Zeilenumbrüche und nachfolgende Inhalte. Eine Ersatzschrift mit ähnlichen Proportionen hält diese Verschiebung klein. Der Inhalt bleibt in jedem Fall von Anfang an lesbar.
