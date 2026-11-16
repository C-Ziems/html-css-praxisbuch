# Aufgaben und Lösungsvorschläge zu Kapitel 64: Weitere Techniken der Webentwicklung einordnen

## Aufgabe 1

**Aufgabe:** Ein CSS-Framework liegt als `css/framework.css` vor. Schreibe die Sammeldatei `style.css` so, dass unsere drei Module für normale Deklarationen Vorrang haben, und erkläre, wann das Framework trotzdem gewinnt.

**Lösungsvorschlag**

```css
@layer framework, basis, komponenten, druck;
@import url("css/framework.css") layer(framework);
@import url("css/basis.css") layer(basis);
@import url("css/komponenten.css") layer(komponenten);
@import url("css/druck.css") layer(druck) print;
```

Die Ebene `framework` steht zuerst und hat deshalb bei normalen Deklarationen den geringsten Vorrang, unabhängig von der Spezifität ihrer Selektoren. Bei `!important` kehrt sich die Reihenfolge der Ebenen um: Eine wichtige Deklaration im Framework setzt sich dann gegen unsere Ebenen durch.

## Aufgabe 2

**Aufgabe:** Eine Bibliothek stellt ein Bildkarussell bereit. Beantworte für sie die Prüffragen aus Abschnitt 64.7: Beschreibe dein Vorgehen und nenne die wichtigsten Fundstellen.

**Lösungsvorschlag**

- Aufgabe: Brauchen wir ein Karussell überhaupt? Oft genügen eine Bildleiste mit Scroll Snap (Kapitel 51) oder untereinander stehende Bilder.
- Lizenz: Lizenzdatei und Bedingungen in der Dokumentation oder im Repository des Projekts.
- Pflege: Datum der letzten Version, Änderungsprotokoll, offene Sicherheitsmeldungen.
- Größe: Umfang der Dateien und welcher Teil davon benötigt wird.
- Herkunft: Selbst bereitstellen statt von einem fremden Server laden; sonst entsteht ein zusätzlicher Datenfluss (Kapitel 61).
- Zugänglichkeit: Tastaturbedienung, Fokus, Beschriftung der Schaltflächen, keine automatische Bewegung ohne Pause; Test in einem eigenen Testdokument.
