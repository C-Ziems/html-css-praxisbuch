# Aufgaben und Lösungsvorschläge zu Kapitel 38: Validierung und Formularstyling

## Aufgabe 1

**Aufgabe:** Ein Pflichtfeld „Gerätekennung“ soll genau zwei Großbuchstaben, ein Leerzeichen und vier Ziffern verlangen, etwa „HT 2026“. Schreibe das Feld mit einem sichtbaren Hinweis, der mit dem Feld verbunden ist.

**Lösungsvorschlag**

```html
<div class="formularfeld">
    <label for="kennung">Gerätekennung</label>
    <input type="text" id="kennung" name="kennung" required
           pattern="[A-Z]{2} [0-9]{4}" aria-describedby="kennung-hinweis">
    <p id="kennung-hinweis" class="feldhinweis">
        Zwei Großbuchstaben, ein Leerzeichen und vier Ziffern, zum Beispiel HT 2026.
    </p>
</div>
```

`pattern` gilt für den gesamten Wert. Der sichtbare Hinweis erklärt die Regel, bevor ein Fehler entsteht. `aria-describedby` ordnet ihn dem Feld zu, sodass Screenreader ihn zusammen mit dem Feld vorlesen.

## Aufgabe 2

**Aufgabe:** Ein Formular zeigt ungültige Eingaben mit einem Fehlerrahmen an. Erkläre, warum wir ihn mit `:user-invalid` statt mit `:invalid` anzeigen.

**Lösungsvorschlag**

Ein leeres Pflichtfeld entspricht schon beim Laden der Seite `:invalid`. Ein Fehlerrahmen mit `:invalid` würde deshalb einen Fehler anzeigen, bevor jemand etwas eingegeben hat. `:user-invalid` trifft erst zu, nachdem mit dem Feld gearbeitet oder das Absenden versucht wurde. Die Rückmeldung kommt so zum passenden Zeitpunkt.
