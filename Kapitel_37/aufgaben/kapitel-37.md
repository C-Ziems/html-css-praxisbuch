# Aufgaben und Lösungsvorschläge zu Kapitel 37: Formulargruppen, Textbereiche und Auswahllisten

## Aufgabe 1

**Aufgabe:** Ein Bestellformular benötigt einen Bereich „Lieferadresse“ mit den Feldern Straße, Postleitzahl und Ort. Lege ihn als Gruppe an.

**Lösungsvorschlag**

```html
<fieldset>
    <legend>Lieferadresse</legend>
    <div class="formularfeld">
        <label for="strasse">Straße und Hausnummer</label>
        <input type="text" id="strasse" name="strasse" autocomplete="street-address">
    </div>
    <div class="formularfeld">
        <label for="plz">Postleitzahl</label>
        <input type="text" id="plz" name="plz" inputmode="numeric" autocomplete="postal-code">
    </div>
    <div class="formularfeld">
        <label for="ort">Ort</label>
        <input type="text" id="ort" name="ort" autocomplete="address-level2">
    </div>
</fieldset>
```

Die Legende benennt die gemeinsame Aufgabe, die Labels die einzelnen Felder.

## Aufgabe 2

**Aufgabe:** Ein Formular enthält a) die Auswahl eines von fünf festen Räumen und b) eine Gerätebezeichnung mit Vorschlägen, aber freier Eingabe. Entscheide jeweils zwischen `select` und `datalist` und begründe die Entscheidung.

**Lösungsvorschlag**

a) `select`: Es gibt genau fünf gültige Werte, andere Eingaben sollen nicht möglich sein.

b) `input` mit `list` und einer `datalist`: Die Vorschläge erleichtern die Eingabe, freie Bezeichnungen bleiben erlaubt.
