# Aufgaben und Lösungsvorschläge zu Kapitel 10: Links, URLs, Fragmente und Navigation

## Aufgabe 1

**Aufgabe:** Eine Seite enthält die Linktexte „Die Anleitung finden Sie `<a href="anleitung.pdf">hier</a>`.“ und „`<a href="geraete.html">Mehr</a>`“. Formuliere beide so um, dass sie ihr Ziel verständlich benennen.

**Lösungsvorschlag**

```html
<p>Die <a href="anleitung.pdf">Bedienungsanleitung des Thermostats (PDF)</a> beschreibt alle Einstellungen.</p>
<p><a href="geraete.html">Alle Gerätesteckbriefe ansehen</a></p>
```

Der Linktext benennt Ziel oder Zweck auch ohne den umgebenden Satz. Das ist wichtig, weil assistive Technik Links auch als Liste anzeigen kann.

## Aufgabe 2

**Aufgabe:** Eine Testdatei soll drei Abschnitte und davor eine Inhaltsübersicht erhalten. Lege die Abschnitte mit `id` an, verlinke sie mit Fragmentlinks und prüfe die Links mit Tabulatortaste und Enter. Beobachte anschließend, was geschieht, wenn ein Fragment zu keiner `id` passt.

**Lösungsvorschlag**

```html
<nav>
    <ul>
        <li><a href="#erdgeschoss">Erdgeschoss</a></li>
        <li><a href="#obergeschoss">Obergeschoss</a></li>
        <li><a href="#garten">Garten</a></li>
    </ul>
</nav>
<h2 id="erdgeschoss">Erdgeschoss</h2>
<p>…</p>
<h2 id="obergeschoss">Obergeschoss</h2>
<p>…</p>
<h2 id="garten">Garten</h2>
<p>…</p>
```

Passt ein Fragment zu keiner `id`, ändert sich in gängigen Browsern zwar die Adresse in der Adresszeile, die Seite springt aber nicht zum gewünschten Bereich. Eine Fehlermeldung erscheint nicht; solche Fehler fallen nur beim Ausprobieren auf. Halte fest, was dein Browser tatsächlich zeigt.
