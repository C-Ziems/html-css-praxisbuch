# Aufgaben und Lösungsvorschläge zu Kapitel 19: Normal Flow, display, overflow und Sichtbarkeit

## Aufgabe 1

**Aufgabe:** Eine Seite stellt folgende Anforderungen: a) Ein Element soll weder sichtbar noch bedienbar sein und keinen Platz einnehmen. b) Es soll unsichtbar sein, seinen Platz aber behalten. c) Ein langer Text soll in einer Box mit begrenzter Höhe scrollbar sein. d) Links sollen mit Innenabstand nebeneinander im Zeilenfluss stehen. Wähle für jede Anforderung die passende Technik.

**Lösungsvorschlag**

a) `display: none` oder das HTML-Attribut `hidden`

b) `visibility: hidden`

c) eine Höhenbegrenzung, etwa `max-height`, zusammen mit `overflow: auto`

d) `display: inline-block`

## Aufgabe 2

**Aufgabe:** Ein Bedienelement wird mit `opacity: 0` ausgeblendet. Erkläre, warum es für die Tastatur trotzdem nicht verborgen ist.

**Lösungsvorschlag**

`opacity: 0` macht ein Element nur durchsichtig. Es behält seinen Platz, kann weiterhin den Fokus erhalten und wird von Screenreadern vorgelesen. Mit der Tabulatortaste landet man deshalb auf einem unsichtbaren Element und sieht nicht, was gerade bedient wird. Soll ein Bedienelement nicht erreichbar sein, verwenden wir `display: none`, `hidden` oder, wenn es seinen Platz behalten soll, `visibility: hidden`.
