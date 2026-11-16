# Aufgaben und Lösungsvorschläge zu Kapitel 44: CSS Nesting, @scope und @layer

## Aufgabe 1

**Aufgabe:** Die folgenden Regeln gehören zu einer Karte. Fasse sie mit nativer Verschachtelung zusammen:

```css
.karte { padding: 1rem; }
.karte h3 { margin-block-start: 0; }
.karte:hover { box-shadow: var(--schatten-karte); }
```

**Lösungsvorschlag**

```css
.karte {
    padding: 1rem;

    h3 {
        margin-block-start: 0;
    }

    &:hover {
        box-shadow: var(--schatten-karte);
    }
}
```

Die verschachtelte Regel `h3` wählt Nachfahren der Karte. Für `:hover` am selben Element steht `&` für den äußeren Selektor.

## Aufgabe 2

**Aufgabe:** Für einen Link in `#navigation` gelten die folgenden Regeln. Gib an, welche Farbe er erhält, und begründe deine Antwort:

```css
@layer basis, komponenten;
@layer komponenten { a { color: green; } }
@layer basis { #navigation a { color: red; } }
a { color: blue; }
```

**Lösungsvorschlag**

Der Link wird blau. Normale Deklarationen außerhalb aller Layer haben Vorrang vor allen Deklarationen in Layern, unabhängig von der Spezifität. Ohne die Regel `a { color: blue; }` wäre er grün: Die Ebene `komponenten` ist später genannt und hat Vorrang vor `basis`, obwohl `#navigation a` spezifischer ist.
