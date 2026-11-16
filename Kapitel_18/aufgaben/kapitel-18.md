# Aufgaben und Lösungsvorschläge zu Kapitel 18: Boxmodell, Größen und Abstände

## Aufgabe 1

**Aufgabe:** Ein Element hat `width: 300px; padding: 20px; border: 2px solid; margin: 10px;`. Bestimme für `content-box` und für `border-box`, wie breit die Box bis zur Rahmenkante ist und wie viel Platz sie einschließlich Außenabstand benötigt.

**Lösungsvorschlag**

| | bis zur Rahmenkante | mit Außenabstand |
|---|---|---|
| `content-box` | 300 + 2 × 20 + 2 × 2 = 344 px | 344 + 2 × 10 = 364 px |
| `border-box` | 300 px | 320 px |

Bei `border-box` schließt `width` Innenabstand und Rahmen ein; für den Inhalt bleiben 300 − 40 − 4 = 256 px.

## Aufgabe 2

**Aufgabe:** Zwei unmittelbar aufeinanderfolgende Absätze stehen im normalen Blockfluss, ohne weitere Inhalte dazwischen. Der erste hat `margin-bottom: 1rem`, der zweite `margin-top: 1.5rem`. Gib den Abstand zwischen ihren Rahmenkanten an und begründe ihn.

**Lösungsvorschlag**

Der Abstand beträgt 1,5rem. Im normalen Blockfluss fallen die vertikalen Außenabstände unmittelbar aufeinanderfolgender Blockboxen zusammen, wenn nichts zwischen ihnen steht. Bei positiven Werten gilt der größere; sie werden nicht addiert.
