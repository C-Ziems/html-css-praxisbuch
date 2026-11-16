# Aufgaben und Lösungsvorschläge zu Kapitel 15: Grundlagen der Typografie

## Aufgabe 1

**Aufgabe:** Eine Seite soll zuerst Georgia, dann Times New Roman und zuletzt eine generische Familie verwenden. Schreibe die Schriftfamilienliste und begründe, wo Anführungszeichen stehen.

**Lösungsvorschlag**

```css
font-family: Georgia, "Times New Roman", serif;
```

Den mehrteiligen Familiennamen „Times New Roman“ setzen wir zur besseren Lesbarkeit in Anführungszeichen. Die generische Familie `serif` steht dagegen ohne Anführungszeichen. In Anführungszeichen würde sie als Name einer konkreten Schrift gelesen, die „serif“ heißt.

## Aufgabe 2

**Aufgabe:** Links sollen eine Unterstreichung mit 2 Pixeln Stärke und eigener Farbe erhalten. Schreibe die Regel und erkläre, warum wir die Unterstreichung nicht einfach entfernen.

**Lösungsvorschlag**

```css
a {
    text-decoration-thickness: 2px;
    text-decoration-color: #6b7280;
}
```

Die Unterstreichung macht Links im Fließtext erkennbar, ohne dass die Farbe die einzige Unterscheidung ist. Menschen, die Farben schlecht unterscheiden, erkennen Links sonst nur schwer. Wir gestalten die Unterstreichung deshalb, statt sie zu entfernen.
