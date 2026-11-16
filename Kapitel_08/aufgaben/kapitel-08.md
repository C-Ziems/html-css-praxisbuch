# Aufgaben und Lösungsvorschläge zu Kapitel 8: Textsemantik II: Zitate, Code und Daten

## Aufgabe 1

**Aufgabe:** Eine Anleitung enthält den Satz „Wir drücken Strg + S, und VS Code zeigt kurz ‚Gespeichert‘ an. Die Regel color: navy; steht in style.css.“ Zeichne den Satz vollständig mit den passenden Elementen aus.

**Lösungsvorschlag**

```html
<p>Wir drücken <kbd><kbd>Strg</kbd> + <kbd>S</kbd></kbd>, und VS Code zeigt kurz
<samp>Gespeichert</samp> an. Die Regel <code>color: navy;</code> steht in
<code>style.css</code>.</p>
```

- `kbd` kennzeichnet die Eingabe; die äußere Auszeichnung umfasst die ganze Tastenkombination, die inneren die einzelnen Tasten.
- `samp` kennzeichnet die Ausgabe eines Programms.
- `code` kennzeichnet die CSS-Deklaration und den Dateinamen.

## Aufgabe 2

**Aufgabe:** Ein Gerätepass nennt die Angabe „Wartung fällig am 3. März 2027 um 10 Uhr“. Zeichne sie so aus, dass das Datum maschinenlesbar ist.

**Lösungsvorschlag**

```html
<p>Wartung fällig am <time datetime="2027-03-03T10:00">3. März 2027 um 10 Uhr</time>.</p>
```

Der sichtbare Text bleibt für Menschen formuliert, `datetime` enthält Datum und Uhrzeit in maschinenlesbarer Form.
