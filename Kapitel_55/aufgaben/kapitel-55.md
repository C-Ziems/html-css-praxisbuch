# Aufgaben und Lösungsvorschläge zu Kapitel 55: Sprache, Ruby-Annotationen und Suchbereiche

## Aufgabe 1

**Aufgabe:** Ein Text enthält den Satz „Der Smart Plug Pro trägt die Kennung ZS 2026.“ Gib die englische Sprache des Produktnamens an und nimm die Kennung von automatischer Übersetzung aus.

**Lösungsvorschlag**

```html
<p>Der <span lang="en">Smart Plug Pro</span> trägt die Kennung
<span translate="no">ZS 2026</span>.</p>
```

`lang="en"` sorgt für die richtige Aussprache durch Screenreader und passende Silbentrennung. `translate="no"` verhindert, dass automatische Übersetzungsdienste die Kennung verändern.

## Aufgabe 2

**Aufgabe:** Ein `span` steht ohne eigenes `lang` in einem Absatz mit `lang="en"`. Erkläre, ob `[lang="en"]` und ob `:lang(en)` auf das `span` zutrifft.

**Lösungsvorschlag**

`[lang="en"]` trifft nicht zu, denn das `span` besitzt das Attribut nicht selbst. `:lang(en)` trifft zu, denn es berücksichtigt die geerbte Sprache. `:lang(en)` erfasst außerdem Untervarianten wie `en-GB`, der Attributselektor nur den genauen Wert.
