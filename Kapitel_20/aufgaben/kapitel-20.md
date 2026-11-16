# Aufgaben und Lösungsvorschläge zu Kapitel 20: Semantische Seitenstruktur

## Aufgabe 1

**Aufgabe:** Ein Blogartikel besteht aus einem Kopf mit Titel und Datum, mehreren Inhaltsabschnitten, einem Kasten „Weiterführende Links“ und einem Kontakt zum Autor. Wähle passende Strukturelemente und lege ein HTML-Gerüst an.

**Lösungsvorschlag**

```html
<article>
    <header>
        <h1>Unser Weg zum vernetzten Zuhause</h1>
        <p><time datetime="2026-11-15">15. November 2026</time></p>
    </header>
    <section>
        <h2>Die Planung</h2>
        <p>…</p>
    </section>
    <section>
        <h2>Die ersten Geräte</h2>
        <p>…</p>
    </section>
    <aside>
        <h2>Weiterführende Links</h2>
        <ul>
            <li><a href="…">…</a></li>
        </ul>
    </aside>
    <footer>
        <address>
            Kontakt zum Autor: <a href="mailto:autor@example.com">autor@example.com</a>
        </address>
    </footer>
</article>
```

- `article`: Der Beitrag ist in sich geschlossen.
- `header`: Titel und Datum leiten den Artikel ein.
- `section`: Jeder Abschnitt hat ein eigenes Thema mit Überschrift.
- `aside`: Die Links ergänzen den Artikel, gehören aber nicht zu seinem Hauptinhalt.
- `address` im `footer` des Artikels: Die Kontaktangabe gilt für dieses `article`.

Andere Fassungen sind vertretbar, wenn die Begründung trägt. Gelten die weiterführenden Links für die ganze Seite und nicht nur für diesen Beitrag, kann das `aside` auch außerhalb des `article` stehen. Die Kontaktangabe darf ebenso im `header` des Artikels stehen.

## Aufgabe 2

**Aufgabe:** Das folgende Gerüst enthält zwei Schwachstellen. Erkläre, warum die beiden sichtbaren `main`-Elemente unzulässig sind, und prüfe, ob der Begrüßungsabsatz eine eigene `section` braucht. Erstelle eine begründete Fassung:

```html
<body>
    <main>
        <section>
            <p>Willkommen im Smart Home.</p>
        </section>
    </main>
    <main>…</main>
</body>
```

**Lösungsvorschlag**

1. Ein Dokument darf nur ein sichtbares `main`-Element enthalten. Das ist eine Regel des HTML-Standards; ein zweites sichtbares `main` ist ein Fehler. Der Inhalt des zweiten gehört in das erste `main`.
2. Die `section` ist kein Regelverstoß, aber eine Frage der Gliederung. Eine `section` beschreibt einen thematischen Abschnitt, der typischerweise eine eigene Überschrift trägt. Ein einzelner Begrüßungsabsatz bildet keinen solchen Abschnitt. Er kann deshalb unmittelbar im Hauptinhalt stehen.

```html
<body>
    <main>
        <p>Willkommen im Smart Home.</p>
        …
    </main>
</body>
```

Soll die Begrüßung später zu einem eigenen Thema mit mehreren Inhalten ausgebaut werden, ist eine `section` mit passender Überschrift ebenfalls eine begründete Lösung.
