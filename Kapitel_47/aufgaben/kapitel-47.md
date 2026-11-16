# Aufgaben und Lösungsvorschläge zu Kapitel 47: Container Queries: Komponenten an ihren Platz anpassen

## Aufgabe 1

**Aufgabe:** Eine Produktkarte zeigt bei einer Inhaltsbreite unter 20rem das Bild über dem Text, ab 20rem daneben. Schreibe Container und Abfrage.

**Lösungsvorschlag**

```html
<article class="produktkarte">
    <div class="produktkarte-inhalt">
        <img src="bilder/thermostat.png" alt="…" width="400" height="300">
        <div>
            <h3>Thermostat</h3>
            <p>…</p>
        </div>
    </div>
</article>
```

```css
.produktkarte {
    container: produktkarte / inline-size;
}

.produktkarte-inhalt {
    display: grid;
    gap: 1rem;
}

@container produktkarte (inline-size >= 20rem) {
    .produktkarte-inhalt {
        grid-template-columns: 8rem 1fr;
        align-items: start;
    }
}
```

Die Karte ist der Container, die Abfrage gestaltet ihren Nachfahren `.produktkarte-inhalt`.

## Aufgabe 2

**Aufgabe:** Eine Karte soll sich in einer Container Query auf ihre eigene Breite beziehen. Erkläre, warum das nicht möglich ist, und wie man das löst.

**Lösungsvorschlag**

Eine Container Query gestaltet die Nachfahren eines Containers. Würde ein Element seine eigene Gestaltung von seiner Breite abhängig machen, könnte die geänderte Gestaltung wiederum seine Breite ändern; das ergäbe einen Kreislauf. `container-type: inline-size` isoliert deshalb die Breite des Containers von seinem Inhalt. Soll sich die Karte selbst ändern, machen wir ein umgebendes Element zum Container oder gestalten, wie in Aufgabe 1, ein inneres Element.
