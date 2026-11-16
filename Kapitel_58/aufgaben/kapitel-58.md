# Aufgaben und Lösungsvorschläge zu Kapitel 58: Dokumentinformationen und Favicon vervollständigen

## Aufgabe 1

**Aufgabe:** Die Website „Mein Smart Home“ erhält eine Seite „Kontakt“. Ihre Beschreibung nennt das Modell "ZS 2026" in geraden Anführungszeichen. Schreibe Titel und Beschreibung.

**Lösungsvorschlag**

```html
<title>Kontakt | Mein Smart Home</title>
<meta name="description" content="Kontakt und Service zu unseren Geräten, etwa zum Modell &quot;ZS 2026&quot;.">
```

Der Titel nennt zuerst die Seite, dann die Website. Gerade Anführungszeichen innerhalb eines doppelt begrenzten Attributwerts schreiben wir als `&quot;`.

## Aufgabe 2

**Aufgabe:** Ein Steckbrief beschreibt den Rauchmelder mit dem Modell RM 2026. Zeichne ihn mit Microdata nach schema.org aus: Name, Modell und Beschreibung.

**Lösungsvorschlag**

```html
<article itemscope itemtype="https://schema.org/Product">
    <h2 itemprop="name">Rauchmelder</h2>
    <p>Modell <span itemprop="model">RM 2026</span> mit LED-Anzeige</p>
    <p itemprop="description">Der Rauchmelder warnt in der Küche frühzeitig vor Rauch.</p>
</article>
```

`itemscope` beginnt den Datensatz, `itemtype` nennt den Typ, `itemprop` kennzeichnet die Eigenschaften am sichtbaren Inhalt.
