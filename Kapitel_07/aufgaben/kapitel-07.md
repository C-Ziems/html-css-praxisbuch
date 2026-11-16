# Aufgaben und Lösungsvorschläge zu Kapitel 7: Textsemantik I: Betonung, Wichtigkeit und Textauszeichnung

## Aufgabe 1

**Aufgabe:** Ein Text enthält folgende Angaben: a) die gesprochene Betonung auf „nicht“ in „Bitte das Fenster nicht öffnen“, b) den Warnhinweis „Batterie nur mit Schutzhandschuhen wechseln“, c) den englischen Fachbegriff „smart meter“, d) die Angabe „21 °C“, die nicht umbrechen soll. Wähle für jede Angabe das passende Element oder die passende Zeichenreferenz und begründe deine Wahl.

**Lösungsvorschlag**

```html
<p>Bitte das Fenster <em>nicht</em> öffnen.</p>
<p><strong>Batterie nur mit Schutzhandschuhen wechseln.</strong></p>
<p>Der Zähler ist ein <i lang="en">smart meter</i>.</p>
<p>Solltemperatur: 21&nbsp;°C</p>
```

a) `em` gibt die gesprochene Betonung wieder; sie verändert die Aussage des Satzes.

b) `strong` kennzeichnet Wichtigkeit, hier einen Sicherheitshinweis.

c) `i` hebt einen Ausdruck aus einer anderen Sprache hervor, `lang="en"` nennt die Sprache. Soll der Ausdruck nicht hervorgehoben werden, genügt `<span lang="en">`.

d) `&nbsp;` verhindert einen Zeilenumbruch zwischen Zahl und Einheit.

## Aufgabe 2

**Aufgabe:** Ein Angebot nennt einen alten Preis von 49 € und einen neuen von 39 €. Schreibe beide Varianten: einmal mit `s` als überholte Angabe und einmal mit `del` und `ins` als dokumentierte Änderung. Erkläre anschließend, wann welche Lösung passt.

**Lösungsvorschlag**

Überholte Angabe:

```html
<p>Preis: <s>49&nbsp;€</s> 39&nbsp;€</p>
```

Dokumentierte Änderung:

```html
<p>Preis: <del>49&nbsp;€</del> <ins>39&nbsp;€</ins></p>
```

`s` passt, wenn der alte Preis nur noch zur Information sichtbar bleibt, etwa bei einem Sonderangebot. `del` und `ins` passen, wenn ausdrücklich nachvollziehbar sein soll, dass das Dokument geändert wurde.
