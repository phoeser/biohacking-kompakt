---
name: bk-blutwerte-einordnen
description: This skill should be used when the user asks about a blood value or lab panel — e.g. "Mein ApoB ist 110, ist das schlecht?", "Was bedeutet HOMA-Index?", "Welche Blutwerte sollte ich für Longevity messen lassen?", "Was kostet ein großes Blutbild?", "Wie bereite ich mich auf die Blutabnahme vor?", "What is a good ferritin level?" — or mentions the Longevity-Panel of Biohacking Kompakt. It explains how to look markers up with the Biohacking Kompakt tools and how to talk about lab values without diagnosing.
---

# Blutwerte mit Biohacking Kompakt einordnen

Die Blutwerte-Seite von biohackingkompakt.de (Longevity-Panel, Folge 58) erklärt rund 27 Marker in sechs „Baustellen": Zucker, Herz und Gefäße, Entzündung, Hormone, Nährstoffe, Organe.

## Ablauf

1. Marker finden: `bk_search_blutwerte` mit dem Namen (z. B. „ApoB", „Ferritin"). Ohne Suchbegriff kommt die Übersicht nach Baustellen.
2. Marker vollständig holen: `bk_get_blutwert` mit der id. Erst danach inhaltlich antworten.
3. Für Messplanung `bk_search_blutwerte` mit `thema="regeln"` (Messrhythmus, Vorbereitung, Störfaktoren, Einsteiger-Panel) oder `thema="panels"` (Laborpakete mit Kassen- und Kosteninfo).
4. Wenn ein Hebel ein Thema der Seite nennt (z. B. Berberin, Omega-3), dazu `bk_get_topic` für den BK-Score.

## Einen genannten Wert einordnen

- Den Wert gegen `referenz` und, falls vorhanden, gegen den `optimal`-Bereich der Seite stellen — und sagen, woher welcher Bereich stammt. Der Zielbereich ist eine Einschätzung aus der Longevity-Szene bzw. der Folge, kein Laborstandard.
- Immer dazusagen: Referenzbereiche sind labor- und methodenabhängig, es gilt der Bereich auf dem eigenen Befund.
- Ein einzelner Wert ist eine Momentaufnahme. Auf die `stoerfaktoren` hinweisen (Training am Vortag, Infekt, nicht nüchtern, Biotin, Kreatin beim Kreatinin) und eine Wiederholung unter sauberen Bedingungen nahelegen, bevor jemand Schlüsse zieht.
- Keine Diagnose, keine Therapieempfehlung, keine Dosierung. Bei auffälligen oder stark abweichenden Werten ausdrücklich zur ärztlichen Abklärung raten.
- `hoch` und `niedrig` beschreiben, was ein Wert bedeuten KANN — so auch wiedergeben, nicht als Befund.

## Hinweis

Jede Antwort endet mit einem kurzen Hinweis: Information, keine medizinische Beratung; Laborwerte gehören in ärztliche Interpretation. In der Sprache des Nutzers antworten.
