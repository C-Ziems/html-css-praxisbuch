# Aufgaben und Lösungsvorschläge zu Kapitel 35: Grundlagen von HTML-Formularen

## Aufgabe 1

**Aufgabe:** Das folgende Formular enthält mehrere Probleme. Finde sie und behebe sie:

```html
<form>
    Name: <input type="text" placeholder="Name">
    <button>Absenden</button>
</form>
```

**Lösungsvorschlag**

```html
<form>
    <label for="name">Name</label>
    <input type="text" id="name" name="name">
    <button type="submit">Absenden</button>
</form>
```

1. Das Feld hat kein `label`. Der Text „Name:“ ist nicht mit dem Feld verbunden, und der Platzhalter verschwindet bei der Eingabe; er ersetzt keine Beschriftung.
2. Ohne `name` wird der eingegebene Wert beim Absenden nicht übermittelt.
3. Empfehlung, kein Fehler: Eine Schaltfläche im Formular sendet auch ohne `type` ab. `type="submit"` macht ihre Aufgabe aber ausdrücklich.

## Aufgabe 2

**Aufgabe:** Ein Formular mit `action="suche.html"` und `method="get"` enthält ein Feld mit `name="begriff"`. Eingegeben wird „smarte Lampe“. Gib die entstehende Adresse an.

**Lösungsvorschlag**

```
suche.html?begriff=smarte+Lampe
```

Bei GET hängt der Browser die Daten als Abfrageteil an die Zieladresse an. Das Leerzeichen wird dabei kodiert, in Formulardaten als `+`. Die Adresse `suche.html` wird relativ zum aktuellen Dokument aufgelöst.
