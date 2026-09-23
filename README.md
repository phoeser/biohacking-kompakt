# Biohacking Kompakt für Claude und Gemini

Evidenz-Check zu Supplements, Peptiden und Biohacking-Anwendungen direkt im KI-Assistenten. Das Plugin verbindet Claude bzw. Gemini mit der Wissensdatenbank von [biohackingkompakt.de](https://biohackingkompakt.de): über 250 Themen mit Wirkungsweise, Risiken, Quellen und dem **BK-Score**, dazu die Folgen des Podcasts „Biohacking Kompakt".

*English summary: Read-only access to the German evidence database biohackingkompakt.de — supplements, peptides and biohacking practices rated with the BK-Score (state of knowledge, not a verdict on the substance), plus matching podcast episodes. No account, no API key.*

## Was drin ist

- **Remote-MCP-Server** `https://mcp.biohackingkompakt.de/mcp` — sieben Werkzeuge, alle nur lesend, keine Anmeldung
- **Skill „BK-Score einordnen"** (Claude) bzw. **GEMINI.md** (Gemini) — sagt dem Assistenten, wie er nachschlägt und den Score richtig liest

| Werkzeug | Wofür |
|---|---|
| `bk_search_topics` | Themen suchen (Name, Zweitname, Schlagwort) |
| `bk_get_topic` | Einen Eintrag vollständig abrufen: Nutzen, Risiken, Quellen, BK-Score, Podcastfolgen |
| `bk_list_scores` | Themen nach BK-Score filtern, z. B. „gut belegt und positiv" oder „viel Hype, wenig Evidenz" |
| `bk_search_podcast` | Podcastfolgen suchen |
| `bk_get_podcast_episode` | Eine Folge mit Hörlinks abrufen |
| `bk_list_erfahrungen` | Erfahrungsberichte (Einzelbeobachtungen, kein Beleg) |
| `bk_get_zitierregeln` | Hinweise zum korrekten Zitieren und zur Bedeutung der Score-Achsen |

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
