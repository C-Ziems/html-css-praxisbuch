# Aufgaben und Lösungsvorschläge zu Kapitel 6: Überschriften, Absätze und Dokumentgliederung

## Aufgabe 1

**Aufgabe:** Eine Vereinsseite soll folgenden Inhalt darstellen: Vereinsname, Termine (Sommerfest, Jahresversammlung), Ansprechpersonen, Anfahrt (mit dem Bus, mit dem Auto). Erstelle eine passende Gliederung mit `h1` bis `h3` und begründe die Gliederung.

**Lösungsvorschlag**

Eine mögliche Gliederung:

```html
<h1>Sportverein Musterstadt</h1>
<h2>Termine</h2>
<h3>Sommerfest</h3>
<h3>Jahresversammlung</h3>
<h2>Ansprechpersonen</h2>
<h2>Anfahrt</h2>
<h3>Mit dem Bus</h3>
<h3>Mit dem Auto</h3>
```

- Der Vereinsname benennt die ganze Seite und ist deshalb die einzige `h1`.
- Termine, Ansprechpersonen und Anfahrt sind gleichrangige Hauptbereiche (`h2`).
- Sommerfest und Jahresversammlung sind Unterthemen der Termine, Bus und Auto Unterthemen der Anfahrt (`h3`).

Andere Bezeichnungen sind möglich. Entscheidend ist, dass die Ebenen der inhaltlichen Gliederung folgen und keine Ebene übersprungen wird.

## Aufgabe 2

**Aufgabe:** Der folgende Ausschnitt enthält zwei Fehler. Finde sie und schreibe eine korrigierte Fassung:

```html
<h1>Energie</h1>
<h4>Verbrauch heute</h4>
<p>
    <h3>Hinweis</h3>
    Der Verbrauch liegt unter dem Vortag.
</p>
```

**Lösungsvorschlag**

Die beiden Fehler sind unterschiedlicher Art:

1. Gliederungsfehler: Nach der `h1` folgt eine `h4`; die Ebenen `h2` und `h3` werden übersprungen. Das ist gültiges HTML, die Gliederung stimmt aber nicht mit dem Inhalt überein. „Verbrauch heute“ ist ein Unterthema von „Energie“ und erhält deshalb `h2`.
2. Ungültiges HTML: Ein Absatz `p` darf keine Überschrift enthalten. Der Browser beendet den Absatz beim `<h3>` automatisch, sodass ein leerer Absatz entsteht und der Text nicht mehr im Absatz steht.

Korrigierte Fassung:

```html
<h1>Energie</h1>
<h2>Verbrauch heute</h2>
<h3>Hinweis</h3>
<p>Der Verbrauch liegt unter dem Vortag.</p>
```
