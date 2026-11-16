# HTML & CSS: Das Praxisbuch für moderne Websites

**Begleitmaterial zum Buch von Christian Ziems**

Grundlagen, responsive Layouts und Barrierefreiheit nach aktuellen Webstandards.
Mit durchgehendem Projekt, Aufgaben und Lösungen.

Im Buch entsteht Kapitel für Kapitel die Website eines virtuellen Smart Homes: eine Startseite mit Statusübersicht,
eine Hausseite mit Raumübersicht, Grundriss, Bildern, Medien und Tabellen, ein Gerätepass mit Steckbriefen und eine
Einkaufsliste mit Formular. Dieses Repository enthält dazu

- den **Projektstand** nach jedem Kapitel, das den Code verändert,
- die **Aufgaben mit Lösungsvorschlägen** zu jedem Kapitel ab Kapitel 6, als Webseite mit lauffähigen Beispielen
  und als Textdatei,
- die **Bilder, Audio- und Videodateien** des Projekts.

## Online ansehen

Alle Projektstände, Aufgabenseiten und Beispiele lassen sich direkt im Browser öffnen. Die Startseite mit der
Übersicht aller Kapitel: <https://c-ziems.github.io/html-css-praxisbuch/>

## Herunterladen

Über **Code → Download ZIP** oder den direkten Link
<https://github.com/C-Ziems/html-css-praxisbuch/archive/refs/heads/main.zip> erhältst du alle Dateien. Öffne die Seiten wie im Buch über einen lokalen Webserver,
etwa mit Live Server in VS Code. Einige Funktionen, zum Beispiel Untertitel für das Video, arbeiten nicht, wenn die
Datei direkt aus dem Dateisystem geöffnet wird.

## Aufbau

Für jedes Kapitel gibt es einen Ordner `Kapitel_NN` mit bis zu zwei Unterordnern:

```text
Kapitel_24/
├── smart-home/          Projektstand nach Kapitel 24
└── aufgaben/
    ├── index.html       Aufgaben und Lösungsvorschläge
    ├── kapitel-24.md    dieselben Inhalte als Textdatei
    ├── aufgabe-1.html   lauffähiges Beispiel zu Aufgabe 1
    ├── aufgabe-1.css
    └── aufgaben.css     Gestaltung der Aufgabenseite
```

### Projektstände

Die Ordner `smart-home` eignen sich zum Vergleichen mit dem eigenen Stand und zum Einstieg an einer beliebigen Stelle
des Buches. Möchtest du einen Stand verändern, arbeite in einer Kopie. Hat ein Kapitel keinen eigenen Projektstand,
gilt der Stand des nächstniedrigeren Kapitels mit `smart-home`:

| Kapitel | Stand wie in |
|---|---|
| 1 | – (das Projekt beginnt in Kapitel 2) |
| 4, 5 | `Kapitel_03` |
| 16 | `Kapitel_15` |
| 32 | `Kapitel_31` |
| 52 | `Kapitel_51` |
| 54 | `Kapitel_53` |
| 56 | `Kapitel_55` |
| 60 bis 62 | `Kapitel_59` |
| 64 bis 66 | `Kapitel_63` (Teil XI verändert das Projekt nicht mehr) |

Wichtige Etappen:

| Ordner | Neu im Projekt |
|---|---|
| `Kapitel_11` | Gerätepass `geraete.html`, Navigation mit vier Seiten |
| `Kapitel_28` | Ordner `bilder` |
| `Kapitel_31` | Ordner `medien` mit Audio, Video und Untertiteln |
| `Kapitel_44` | CSS in Module aufgeteilt: `style.css` bindet `css/basis.css` und `css/komponenten.css` als Ebenen ein |
| `Kapitel_57` | Druckmodul `css/druck.css` |
| `Kapitel_58` | `favicon.svg` |
| `Kapitel_63` | `.gitignore` (das Git-Repository legen wir wie im Buch selbst an) |

### Aufgaben und Lösungen

Die Datei `aufgaben/index.html` zeigt jede Aufgabe im Wortlaut des Buches. Der Lösungsvorschlag ist zunächst
verborgen und lässt sich aufklappen. Bearbeite jede Aufgabe zuerst selbst in einer eigenen Datei außerhalb des
Smart-Home-Projekts. Wo eine Aufgabe ein lauffähiges Ergebnis hat, führt ein Link zu einem Beispiel
(`aufgabe-1.html` usw.), das du im Browser und mit den DevTools untersuchen kannst. Einige Beispiele haben eine
zusätzliche Datei `…-fehlerhaft.html` mit dem Fehler aus der Aufgabe zum Vergleichen.

Ein Lösungsvorschlag ist eine mögliche Lösung. Andere Bezeichnungen, Werte oder Formulierungen können ebenso
richtig sein, wenn sie die Aufgabe erfüllen und die Begründung trägt. Beim Vergleichen helfen drei Unterscheidungen:

- **Regel oder Entscheidung:** Ungültiger Code verstößt gegen den Standard. Eine unpassende Semantik ist gültig,
  beschreibt den Inhalt aber nicht treffend. Eine Gestaltungsentscheidung kann so oder anders ausfallen.
- **Projekt oder allgemein:** Klassennamen, Tokens und Dateiaufteilung unseres Smart-Home-Projekts sind
  Konventionen dieses Buches, keine Pflicht für jede Website.
- **Beobachtung oder Garantie:** Wo eine Lösung das Verhalten eines Browsers oder Screenreaders beschreibt, gibt sie
  das übliche Ergebnis wieder. Halte fest, was dein eigener Test tatsächlich zeigt.

### Bilder und Medien

Die Ordner `bilder` und `medien` auf oberster Ebene enthalten alle Bild-, Audio- und Videodateien des Projekts.
In den Projektständen liegen jeweils nur die Dateien, die bis zu diesem Kapitel eingebunden sind.

## Lizenz

Quellcode und Begleitmaterial in diesem Repository stehen unter der **MIT-Lizenz**. Du darfst sie verwenden,
verändern und weitergeben, auch in eigenen und kommerziellen Projekten, solange der Lizenzhinweis erhalten bleibt.
Den vollständigen Text enthält die Datei [`LICENSE`](LICENSE).

### Ausnahmen von der MIT-Lizenz

- **Foto der Außenansicht des Hauses:** Die Dateien `haus-aussenansicht-480.jpg`, `haus-aussenansicht-800.jpg` und
  `haus-aussenansicht-1200.jpg` (im Ordner `bilder` und in den Projektständen ab `Kapitel_28`) sind verkleinerte
  Fassungen eines Fotos von [Pixabay](https://pixabay.com/de/photos/haus-architektur-vorgarten-garage-1836070/)
  (Bild 1836070, bereitgestellt von „Pexels“). Sie stehen unter der
  [Pixabay-Inhaltslizenz](https://pixabay.com/de/service/license-summary/), **nicht** unter der MIT-Lizenz.
  Im Rahmen dieses Projekts darfst du sie verwenden und verändern. Einzeln weitergeben oder verkaufen darfst du sie
  nicht. Möchtest du das Foto in einem eigenen Projekt einsetzen, lade es direkt bei Pixabay herunter.
- **Buchtext:** Er ist urheberrechtlich geschützt und nicht Bestandteil dieses Repositorys.

Alle übrigen Bild-, Audio- und Videodateien hat der Autor selbst erstellt; sie stehen wie der Code unter der
MIT-Lizenz. Eine Übersicht aller Dateien mit ihrer Herkunft steht in [`bilder/QUELLEN.md`](bilder/QUELLEN.md).
