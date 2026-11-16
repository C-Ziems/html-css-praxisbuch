# Aufgaben und Lösungsvorschläge zu Kapitel 32: Eingebettete Inhalte, iframe, object, SVG und canvas

## Aufgabe 1

**Aufgabe:** Eine Wetterkarte von `https://wetter.example.com/karte` soll eingebettet werden. Das `iframe` soll einen beschreibenden Titel tragen, keine Herkunftsangabe übermitteln und keine Formulare absenden dürfen. Schreibe das `iframe`.

**Lösungsvorschlag**

```html
<iframe src="https://wetter.example.com/karte"
        title="Wetterkarte für unsere Region"
        referrerpolicy="no-referrer"
        sandbox="allow-scripts"
        width="600" height="400"></iframe>
```

- `title` benennt den Zweck des eingebetteten Dokuments.
- `referrerpolicy="no-referrer"` übermittelt keine Herkunftsangabe.
- `sandbox` schränkt den Kontext ein. Ohne `allow-forms` darf das Dokument keine Formulare absenden. `allow-scripts` erlauben wir nur, wenn die Karte Scripts benötigt.

Ob der Anbieter die Einbettung erlaubt und welche Daten er dabei verarbeitet, prüfen wir zusätzlich.

## Aufgabe 2

**Aufgabe:** Ein Hauswappen als SVG soll seine Farbe per CSS an die Textfarbe anpassen. Begründe, ob es mit `img` oder direkt als `svg` eingebunden wird.

**Lösungsvorschlag**

Direkt als `svg` im HTML. Ein über `img` eingebundenes SVG ist ein eigenes Dokument, das CSS der Seite erreicht seine Formen nicht. Steht das SVG im HTML, wirken unsere Regeln auf seine Formen. Mit `fill="currentColor"` übernehmen sie die aktuelle Textfarbe:

```html
<svg viewBox="0 0 24 24" width="48" height="48" role="img" aria-label="Hauswappen">
    <path d="M12 2 L22 9 V22 H2 V9 Z" fill="currentColor"/>
</svg>
```
