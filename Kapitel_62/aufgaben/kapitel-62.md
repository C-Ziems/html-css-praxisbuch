# Aufgaben und Lösungsvorschläge zu Kapitel 62: Die Website für das Hosting vorbereiten

## Aufgabe 1

**Aufgabe:** Nach dem Upload fehlen Gestaltung und ein Bild. Im Netzwerkbereich zeigt `style.css` den Status 200 mit `Content-Type: text/plain`, und `Bilder/grundriss.png` den Status 404, obwohl die Datei als `bilder/grundriss.png` hochgeladen wurde. Gib die Ursachen und Lösungen an.

**Lösungsvorschlag**

1. Der Server liefert `style.css` mit dem falschen Medientyp aus. Browser wenden ein Stylesheet mit `text/plain` nicht an. Die Lösung liegt in der Serverkonfiguration: `.css` muss als `text/css` ausgeliefert werden.
2. Im HTML steht `Bilder/grundriss.png`, die Datei heißt `bilder/grundriss.png`. Auf dem Server wird Groß- und Kleinschreibung unterschieden. Wir korrigieren den Pfad im HTML auf die tatsächliche Schreibweise.

## Aufgabe 2

**Aufgabe:** Ein Projektordner enthält `.git`, `notizen.txt`, `entwurf-alt.html`, `index.html`, `style.css`, `css/` und `bilder/`. Nenne die Dateien und Ordner, die veröffentlicht werden, und begründe die Auswahl.

**Lösungsvorschlag**

Veröffentlicht werden `index.html`, `style.css` sowie die Ordner `css/` und `bilder/` mit ihrem Inhalt, dazu die übrigen benötigten Seiten. `.git` ist die Versionsverwaltung, `notizen.txt` eine interne Notiz und `entwurf-alt.html` ein überholter Entwurf; sie gehören nicht in den öffentlichen Bereich. Wir wählen die Dateien bewusst aus, statt den Arbeitsordner vollständig zu übertragen.
