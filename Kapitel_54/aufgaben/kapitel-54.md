# Aufgaben und Lösungsvorschläge zu Kapitel 54: Webstandards, Browserunterstützung und Referenzen prüfen

## Aufgabe 1

**Aufgabe:** Ein Textbereich soll mit `field-sizing: content` mit seinem Inhalt wachsen. Lege dafür eine Prüfnotiz nach dem Muster aus Abschnitt 54.7 an: Funktion, Aufgabe, benötigte Teilfunktion, Ersatzverhalten, geprüfte Browser und Entscheidung.

**Lösungsvorschlag**

Ein mögliches Ergebnis; die Angaben zu Browsern und Versionen hängen vom Prüfzeitpunkt ab:

| Feld | Eintrag |
|---|---|
| Funktion | `field-sizing: content` an `textarea` |
| Aufgabe | Der Textbereich soll mit seinem Inhalt wachsen, statt eine Scrollleiste zu zeigen. |
| Benötigte Teilfunktion | Wert `content` der Eigenschaft `field-sizing` für `textarea` |
| Ersatzverhalten | Der Textbereich behält seine feste Größe und wird bei längerem Text scrollbar; er bleibt nutzbar. |
| Geprüfte Browser | Je ein aktueller Browser jeder Engine mit Version und Prüfdatum |
| Entscheidung | Kann als Verbesserung ergänzt werden, weil das Ersatzverhalten brauchbar ist; eine `max-block-size` begrenzt das Wachstum. |

Quellen: Eigenschaftsdefinition in der CSS-Spezifikation, Referenzseite bei MDN Web Docs mit Kompatibilitätstabelle, eigener Test.

## Aufgabe 2

**Aufgabe:** Ein Browser kennt ein HTML-Attribut nicht. Erkläre, warum keine Fehlermeldung entsteht und wie wir die fehlende Unterstützung trotzdem bemerken.

**Lösungsvorschlag**

HTML ist fehlertolerant: Ein unbekanntes Attribut bleibt als gewöhnliches Attribut im DOM stehen, ohne Wirkung und ohne Meldung. Das sorgt dafür, dass ältere Browser neue Seiten nicht abbrechen. Bemerken können wir die fehlende Unterstützung nur am Verhalten: durch eigene Tests in den Zielbrowsern und durch die Kompatibilitätsdaten der einzelnen Attribute.
