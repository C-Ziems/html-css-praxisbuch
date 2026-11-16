# Aufgaben und Lösungsvorschläge zu Kapitel 39: Fortgeschrittene Selektoren und Pseudoklassen

## Aufgabe 1

**Aufgabe:** Ein Stylesheet soll folgende Elemente auswählen: a) den Absatz unmittelbar nach einer `h2`, b) alle Links, deren Adresse mit `https://` beginnt, c) jede zweite Zeile im `tbody` einer Tabelle, d) ein `div.formularfeld`, das ein Feld mit `:user-invalid` enthält. Schreibe die passenden Selektoren.

**Lösungsvorschlag**

```css
h2 + p { }                                  /* a) */
a[href^="https://"] { }                     /* b) */
tbody tr:nth-child(even) { }                /* c) */
div.formularfeld:has(:user-invalid) { }     /* d) */
```

a) `+` wählt nur das unmittelbar folgende Geschwister. b) `^=` prüft den Anfang des Attributwerts. c) `even` entspricht `2n`. d) `:has()` prüft vom Container aus, ob ein Nachfahre zutrifft.

## Aufgabe 2

**Aufgabe:** Zwei Regeln verwenden die Selektoren `:is(#kopf, .titel) a` und `:where(#kopf, .titel) a`. Bestimme ihre Spezifität und erkläre den Unterschied.

**Lösungsvorschlag**

- `:is(#kopf, .titel) a`: 1-0-1. `:is()` übernimmt die Spezifität des spezifischsten Arguments, hier `#kopf`, unabhängig davon, welches Argument tatsächlich zutrifft.
- `:where(#kopf, .titel) a`: 0-0-1. `:where()` trägt keine Spezifität bei, es zählt nur `a`.

Mit `:where()` lassen sich Grundregeln schreiben, die später leicht überstimmt werden können.
