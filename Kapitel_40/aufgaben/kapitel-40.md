# Aufgaben und Lösungsvorschläge zu Kapitel 40: Pseudoelemente und generierte Darstellung

## Aufgabe 1

**Aufgabe:** Links zu anderen Websites sollen einen nachgestellten Pfeil „↗“ erhalten. Schreibe die Regel und erkläre, warum der Hinweis „externe Seite“ nicht allein im generierten Inhalt stehen sollte.

**Lösungsvorschlag**

```css
a[href^="https://"]::after {
    content: " ↗";
}
```

Generierter Inhalt wird von assistiven Technologien unterschiedlich behandelt: Manche lesen den Pfeil vor, manche nicht, und seine Bedeutung ist nicht eindeutig. Dass ein Link die Website verlässt, gehört deshalb in den Linktext, etwa „Herstellerseite (externe Website)“. Der Pfeil unterstützt diese Information nur.

Der Selektor trifft alle absoluten HTTPS-Adressen, auch solche auf die eigene Website. In unserem Projekt verwenden wir für eigene Seiten relative Pfade, deshalb passt er hier.

## Aufgabe 2

**Aufgabe:** Die Marker einer geordneten Liste sollen fett und in der Akzentfarbe erscheinen. Schreibe die Regel.

**Lösungsvorschlag**

```css
ol li::marker {
    font-weight: bold;
    color: var(--farbe-akzent);
}
```

`::marker` erlaubt nur bestimmte Eigenschaften, darunter Farbe und Schrifteigenschaften.
