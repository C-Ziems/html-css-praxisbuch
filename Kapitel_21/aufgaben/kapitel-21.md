# Aufgaben und Lösungsvorschläge zu Kapitel 21: Positionierung und Stapelreihenfolge

## Aufgabe 1

**Aufgabe:** Ein Abzeichen „Neu“ soll oben rechts in einer Karte stehen. Schreibe den HTML-Ausschnitt und das CSS.

**Lösungsvorschlag**

```html
<article class="karte">
    <h3>Thermostat</h3>
    <p class="abzeichen">Neu</p>
    <p>Regelt die Raumtemperatur.</p>
</article>
```

```css
.karte {
    position: relative;
}

.karte > h3 {
    padding-right: 4rem;
}

.abzeichen {
    position: absolute;
    top: 0.5rem;
    right: 0.5rem;
    margin: 0;
}
```

`position: relative` macht die Karte zum Bezug für das absolut positionierte Abzeichen. Der Innenabstand der Überschrift verhindert, dass das Abzeichen den Titel überdeckt.

## Aufgabe 2

**Aufgabe:** Die Boxen A und B sind positionierte Geschwister im selben Stacking Context. A hat `z-index: 3` und bildet damit einen eigenen Stacking Context, ein Kind darin hat `z-index: 100`. B hat `z-index: 5`. Gib an, was oben liegt, und begründe deine Antwort.

**Lösungsvorschlag**

Box B liegt oben, auch über dem Kind mit `z-index: 100`. A und B werden im gemeinsamen übergeordneten Stacking Context verglichen. Box A bildet zugleich einen eigenen Stacking Context. Der Wert 100 entscheidet nur innerhalb von A. Nach außen wird A als Ganzes mit `z-index: 3` gegen B mit `z-index: 5` verglichen.
