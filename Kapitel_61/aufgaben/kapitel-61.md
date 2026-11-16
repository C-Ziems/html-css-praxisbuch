# Aufgaben und Lösungsvorschläge zu Kapitel 61: Datenschutz und Rechte vor der Veröffentlichung prüfen

## Aufgabe 1

**Aufgabe:** Eine Website enthält a) eine Schrift von einem fremden Schriftdienst, b) ein Video eines Videoportals im `iframe` und c) einen gewöhnlichen Link zur Website eines Herstellers. Beschreibe für jede Einbindung, welche zusätzlichen Datenflüsse beim Seitenaufruf entstehen.

**Lösungsvorschlag**

a) Beim Laden der Seite fordert der Browser die Schrift beim fremden Dienst an. Dieser erhält dabei mindestens die IP-Adresse und technische Angaben, ohne dass jemand etwas anklickt.

b) Das `iframe` lädt ein vollständiges Dokument des Portals, das weitere Ressourcen anfordern und Informationen auf dem Endgerät speichern oder auslesen kann. Hier sind Datenverarbeitung und gegebenenfalls Einwilligung genau zu prüfen.

c) Ein gewöhnlicher Link lädt nichts, solange niemand ihn anklickt. Erst beim Aufruf wechselt der Browser zur Zielseite.

Ob und unter welchen Bedingungen eine Einbindung zulässig ist, klären wir anhand der tatsächlichen Verarbeitung; diese Übersicht ersetzt keine rechtliche Prüfung.

## Aufgabe 2

**Aufgabe:** Ein Formular soll von GET auf POST umgestellt werden, weil das sicherer sei. Erkläre, warum POST nicht automatisch sicherer ist.

**Lösungsvorschlag**

POST verlagert die Eingaben aus der Adresse in den Anfragekörper. Sie erscheinen dann nicht im Verlauf oder in der Adresszeile, werden aber genauso unverschlüsselt übertragen, wenn kein HTTPS verwendet wird. Für die Transportverschlüsselung ist HTTPS zuständig. Wie die Daten auf dem Server verarbeitet, gespeichert und geschützt werden, hängt von der Anwendung ab, nicht von der Methode.
