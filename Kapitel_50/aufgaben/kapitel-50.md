# Aufgaben und Lösungsvorschläge zu Kapitel 50: Animationen und @keyframes

## Aufgabe 1

**Aufgabe:** Ein Hinweis soll einmalig eingeblendet werden: Deckkraft von 0 auf 1, Verschiebung von 0.5rem auf 0, Dauer 400 ms. Die Animation läuft nur ohne Präferenz für reduzierte Bewegung, und ohne Animation muss der Hinweis sichtbar sein. Schreibe die Animation.

**Lösungsvorschlag**

```css
@keyframes hinweis-erscheint {
    from {
        opacity: 0;
        transform: translateY(0.5rem);
    }
    to {
        opacity: 1;
        transform: none;
    }
}

@media (prefers-reduced-motion: no-preference) {
    .hinweis {
        animation: hinweis-erscheint 400ms ease-out;
    }
}
```

Der normale Zustand des Hinweises ist sichtbar. Ohne Animation, etwa bei reduzierter Bewegung, erscheint er sofort.

## Aufgabe 2

**Aufgabe:** Zur Animation aus Aufgabe 1 kommt die Regel `.hinweis { opacity: 1 !important; }` hinzu. Beschreibe, was danach noch sichtbar animiert wird, und begründe es mit Abschnitt 50.8.

**Lösungsvorschlag**

Sichtbar animiert wird nur noch die Verschiebung. Nach der Rangfolge in Abschnitt 50.8 überstimmt eine wichtige Deklaration den Animationswert derselben Eigenschaft: Die Deckkraft bleibt während des Ablaufs bei 1. `transform` ist von der wichtigen Deklaration nicht betroffen und wird weiterhin animiert.
