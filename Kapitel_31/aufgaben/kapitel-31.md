# Aufgaben und Lösungsvorschläge zu Kapitel 31: Audio, Video und Untertitel

## Aufgabe 1

**Aufgabe:** Ein Video soll mit Bedienelementen, Vorschaubild, zwei Quelldateien (MP4 und WebM) und einer deutschen Caption-Spur erscheinen. Binde es ein.

**Lösungsvorschlag**

```html
<video controls poster="bilder/rundgang-vorschau.png" width="1280" height="720">
    <source src="medien/rundgang.mp4" type="video/mp4">
    <source src="medien/rundgang.webm" type="video/webm">
    <track kind="captions" src="medien/rundgang-de.vtt" srclang="de" label="Deutsch">
    <p>Das Video kann hier nicht abgespielt werden.
       <a href="medien/rundgang.mp4">Video herunterladen</a></p>
</video>
```

Der Browser verwendet die erste `source`, die er abspielen kann. Der Inhalt nach den `track`-Elementen erscheint nur, wenn der Browser `video` gar nicht unterstützt.

## Aufgabe 2

**Aufgabe:** Ein Video bietet Textspuren der Arten `captions` und `subtitles` an. Erkläre den Unterschied an einem Beispiel.

**Lösungsvorschlag**

`captions` geben Sprache und wichtige Geräusche in der Sprache des Videos wieder, etwa „[Türklingel]“ oder „[Musik setzt ein]“. Sie richten sich an Menschen, die den Ton nicht oder schlecht hören. `subtitles` geben den Dialog als Verschriftlichung oder Übersetzung wieder, etwa englische Untertitel zu einem deutschen Video. Sie richten sich an Menschen, die den Ton hören, das Gesprochene aber nicht verstehen, zum Beispiel wegen der Sprache oder einer lauten Umgebung.
