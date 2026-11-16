# Aufgaben und Lösungsvorschläge zu Kapitel 16: Kaskade, Vererbung und Spezifität

## Aufgabe 1

**Aufgabe:** Für den Link zur aktuellen Seite in `nav.hauptnavigation` gelten die folgenden Regeln. Bestimme die Spezifität jeder Regel und gib die sichtbare Farbe an:

```css
a { color: navy; }
.hauptnavigation a { color: darkblue; }
nav a { color: black; }
[aria-current="page"] { color: purple; }
```

**Lösungsvorschlag**

| Regel | Spezifität |
|---|---|
| `a` | 0-0-1 |
| `.hauptnavigation a` | 0-1-1 |
| `nav a` | 0-0-2 |
| `[aria-current="page"]` | 0-1-0 |

Alle Regeln haben dieselbe Herkunft. Die Kategorien werden von links nach rechts verglichen: Keine Regel besitzt eine ID. Bei Klassen und Attributen haben `.hauptnavigation a` und `[aria-current="page"]` je eins; bei den Typselektoren entscheidet `.hauptnavigation a` mit eins gegenüber null. Der Link erscheint deshalb `darkblue`. Die Reihenfolge spielt keine Rolle mehr.

## Aufgabe 2

**Aufgabe:** Ein Absatz mit der Klasse `hinweis` bleibt schwarz, obwohl `.hinweis { color: brown; }` im Stylesheet steht. Nenne mögliche Ursachen in der Reihenfolge der Prüfschritte aus diesem Kapitel.

**Lösungsvorschlag**

1. Datei: Ist `style.css` gespeichert und im `head` eingebunden?
2. Element: Trägt der Absatz wirklich `class="hinweis"`, ohne Tippfehler?
3. Selektor: Steht im Stylesheet `.hinweis` mit Punkt?
4. Syntax: Sind Klammern und Semikolons vollständig, ist der Wert gültig?
5. Herkunft: Setzt ein Inline-Style am Absatz eine andere Farbe?
6. Kaskade: Überstimmt eine spezifischere oder spätere Regel die Farbe?
7. Vererbung: Gilt die Regel überhaupt für den Absatz selbst, oder erbt er nur einen Wert?

Im Inspector zeigt der Bereich Styles, ob die Regel erscheint und ob sie durchgestrichen ist.
