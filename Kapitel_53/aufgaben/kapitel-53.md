# Aufgaben und Lösungsvorschläge zu Kapitel 53: Aufklappbereiche, Dialoge und Popover

## Aufgabe 1

**Aufgabe:** Eine Seite zeigt drei häufige Fragen, deren Antworten sich aufklappen lassen. Es soll immer nur eine Antwort geöffnet sein, und die erste ist beim Laden geöffnet. Lege die Seite an.

**Lösungsvorschlag**

```html
<h2>Häufige Fragen</h2>
<details name="faq" open>
    <summary>Wie wechsle ich die Batterie?</summary>
    <p>…</p>
</details>
<details name="faq">
    <summary>Wie setze ich das Gerät zurück?</summary>
    <p>…</p>
</details>
<details name="faq">
    <summary>Wo finde ich die Seriennummer?</summary>
    <p>…</p>
</details>
```

Der gemeinsame `name` bildet eine Gruppe, in der sich jeweils nur ein Bereich öffnen lässt. Browser ohne diese Unterstützung öffnen die Bereiche unabhängig voneinander; der Inhalt bleibt erreichbar.

## Aufgabe 2

**Aufgabe:** Eine Schaltfläche „Hilfe“ soll ohne Script ein Popover mit einem kurzen Hilfetext öffnen. Schreibe das HTML und erkläre, worin sich das Popover von einem modalen Dialog unterscheidet.

**Lösungsvorschlag**

```html
<button type="button" popovertarget="hilfe">Hilfe</button>
<div id="hilfe" popover>
    <p>Mit den Pfeiltasten wählen Sie einen Raum aus.</p>
</div>
```

Ein Popover erscheint über der Seite, macht sie aber nicht inaktiv: Die übrige Seite bleibt bedienbar, und ein Klick außerhalb oder Escape schließt es. Ein modaler Dialog macht die übrige Seite inaktiv, bis er geschlossen wird. Er eignet sich für Arbeitsschritte, die zuerst abgeschlossen werden müssen.
