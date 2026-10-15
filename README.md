# Biohacking Kompakt für Claude und Gemini

Evidenz-Check zu Supplements, Peptiden und Biohacking-Anwendungen direkt im KI-Assistenten. Das Plugin verbindet Claude bzw. Gemini mit der Wissensdatenbank von [biohackingkompakt.de](https://biohackingkompakt.de): fast 500 Themen mit Wirkungsweise, Risiken, Quellen und dem **BK-Score**, dazu die Folgen des Podcasts „Biohacking Kompakt".

*English summary: Read-only access to the German evidence database biohackingkompakt.de — supplements, peptides and biohacking practices rated with the BK-Score (state of knowledge, not a verdict on the substance), plus matching podcast episodes. No account, no API key.*

## Was drin ist

- **Remote-MCP-Server** `https://mcp.biohackingkompakt.de/mcp` — sechzehn Werkzeuge, alle nur lesend, keine Anmeldung
- **Skills „BK-Score einordnen" und „Blutwerte einordnen"** (Claude) bzw. **GEMINI.md** (Gemini) — sagen dem Assistenten, wie er nachschlägt und den Score bzw. Laborwerte richtig liest
- **Befehle** `/bk-check`, `/bk-vergleich`, `/bk-blutwert`, `/bk-neu` (Claude)

| Werkzeug | Wofür |
|---|---|
| `bk_search_topics` | Themen suchen (Name, Zweitname, Schlagwort) |
| `bk_get_topic` | Einen Eintrag vollständig abrufen: Nutzen, Risiken, Quellen, BK-Score, Podcastfolgen |
| `bk_list_scores` | Themen nach BK-Score filtern, z. B. „gut belegt und positiv" oder „Werbung weit vor den Daten" |
| `bk_search_podcast` | Podcastfolgen suchen |
| `bk_get_podcast_episode` | Eine Folge mit Hörlinks abrufen |
| `bk_list_erfahrungen` | Erfahrungsberichte (Einzelbeobachtungen, kein Beleg) |
| `bk_get_zitierregeln` | Hinweise zum korrekten Zitieren und zur Bedeutung der Score-Achsen |
| `bk_search_inhalte` | Volltextsuche über alle Seitentexte (Themen, Tipps, Vergleiche, Glossar, Folgen) |
| `bk_get_seite` | Eine Seite vollständig lesen |
| `bk_search_studien` | Die Studien-Datenbank: rund 2.500 Studien mit Studientyp und PubMed-/DOI-Link |
| `bk_compare_topics` | Zwei bis vier Themen im BK-Score nebeneinander |
| `bk_search_blutwerte` | Blutwerte des Longevity-Panels, Laborpakete und Messregeln |
| `bk_get_blutwert` | Ein Marker vollständig: Referenz, Zielbereich, Bedeutung, Hebel, Störfaktoren |
| `bk_get_signalweg` | Signalwege-Atlas: mTOR, AMPK, Sirtuine … und welche Themen dort ansetzen |
| `bk_get_report` | Kennzahlen des Biohacking-Reports, live aus dem Bestand |
| `bk_list_aenderungen` | Was hat sich an Bewertungen geändert – mit Quelle |

### Befehle (Claude)

| Befehl | Wofür |
|---|---|
| `/bk-check <Thema>` | Evidenz-Check zu einem Thema |
| `/bk-vergleich <A> vs <B>` | Themen im BK-Score vergleichen |
| `/bk-blutwert <Marker Wert>` | Einen Blutwert einordnen, z. B. „ApoB 110 mg/dl" |
| `/bk-neu [Thema]` | Neueste Bewertungsänderungen und Folgen |

## Installation

### Claude Code

```
/plugin marketplace add phoeser/biohacking-kompakt
/plugin install biohacking-kompakt@biohacking-kompakt
```

### Claude (Desktop, Web, App) ohne Plugin

Einstellungen → Konnektoren → **Eigenen Konnektor hinzufügen** → Name `Biohacking Kompakt`, URL `https://mcp.biohackingkompakt.de/mcp`. Eine Anmeldung ist nicht nötig.

### Gemini CLI

```
gemini extensions install https://github.com/phoeser/biohacking-kompakt
```

### Andere MCP-fähige Programme

Streamable-HTTP-Endpunkt: `https://mcp.biohackingkompakt.de/mcp` (ohne Authentifizierung).

## Beispielfragen

- „Wie gut ist Kreatin eigentlich belegt?"
- „Welche Supplements sind gut untersucht und zeigen einen Nutzen?"
- „Wo ist der Hype größer als die Evidenz?"
- „Ist BPC-157 am Menschen untersucht?"
- „Gibt es eine Podcastfolge zu Magnesium?"
- „Mein ApoB ist 110 mg/dl – was heißt das?"
- „Kreatin oder Beta-Alanin?"
- „Was hemmt mTOR, und was aktiviert AMPK?"
- „Wie viel im Biohacking ist überhaupt gut belegt?"

## Den BK-Score richtig lesen

Der BK-Score bewertet den **Wissensstand** zu einem Thema, nicht die Substanz. Eine hohe Human-Evidenz heißt „viel untersucht" — wohin die Daten zeigen, sagt die Richtung. Eine hohe Sicherheits-Datenlage heißt „gut untersucht", nicht „harmlos". Eine hohe Anwendungserfahrung ist kein Wirksamkeitsbeleg. Die Vergaberegeln stehen auf [biohackingkompakt.de/#score](https://biohackingkompakt.de/#score).

Bei experimentellen Substanzen und Peptiden liefert der Server bewusst keine Dosierung und keine Einnahmehinweise.

## Wichtiger Hinweis

Alle Inhalte dienen der Information und ersetzen keine ärztliche Beratung, Diagnose oder Behandlung. Der BK-Score ist eine redaktionelle Einschätzung von Biohacking Kompakt nach offengelegten Regeln, kein wissenschaftliches Urteil und keine Empfehlung.

## Datenschutz

Siehe [PRIVACY.md](PRIVACY.md). Kurz: keine Anmeldung, keine Cookies, keine Profilbildung. Der Server sieht nur die einzelne Werkzeuganfrage, nie die Unterhaltung.

## Support

kontakt@biohackingkompakt.de · [Impressum](https://biohackingkompakt.de/impressum.html)

## Lizenz

MIT für die Dateien in diesem Repository (Plugin- und Erweiterungs-Konfiguration, Skill-Text). Die Inhalte der Datenbank selbst bleiben bei Biohacking Kompakt.
