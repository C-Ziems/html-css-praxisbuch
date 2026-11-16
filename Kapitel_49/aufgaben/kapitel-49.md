# Aufgaben und Lösungsvorschläge zu Kapitel 49: Transformationen und Zustandsübergänge mit CSS

## Aufgabe 1

**Aufgabe:** Eine Karte soll sich beim Überfahren und beim Fokus innerhalb der Karte um 2 Pixel anheben, mit einem Übergang von 150 ms und nur ohne Präferenz für reduzierte Bewegung. Schreibe die Regeln.

**Lösungsvorschlag**

```css
@media (prefers-reduced-motion: no-preference) {
    .karte {
        transition: transform 150ms ease;
    }

    .karte:hover,
    .karte:focus-within {
        transform: translateY(-2px);
    }
}
```

Die Karte selbst ist nicht fokussierbar. `:focus-within` trifft zu, wenn ein Element darin, etwa ein Link, den Fokus hat. Bei reduzierter Bewegung entfällt die Verschiebung; eine Rückmeldung ohne Bewegung, etwa ein Schatten, kann außerhalb der Abfrage stehen.

## Aufgabe 2

**Aufgabe:** Ein Stylesheet verwendet `transition: all`. Erkläre, warum wir das vermeiden.

**Lösungsvorschlag**

`all` erfasst jede animierbare Eigenschaft, auch solche, die später hinzukommen oder sich nebenbei ändern, etwa Größen oder Farben bei einem Farbschemawechsel. Das kann unerwartete Übergänge auslösen und unnötig Rechenaufwand verursachen. Nennen wir die Eigenschaften ausdrücklich, ist klar, was sich bewegt, und die Präferenz für reduzierte Bewegung lässt sich gezielt berücksichtigen.
