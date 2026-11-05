# CLAUDE.md

Hinweise für Claude Code zur Arbeit in diesem Repository.

## Projekt

**vereina** ist ein Verwaltungs- und Organisationstool für Vereine. Ziel ist es, ehrenamtlich
Tätigen Verwaltungs-, Organisations- und Planungsarbeit abzunehmen, damit sie sich auf die
eigentliche Vereinsarbeit konzentrieren können. Details zur Vision stehen in der
[README.md](README.md).

Das Projekt befindet sich in der Anfangsphase – es gibt noch keinen festgelegten Tech-Stack.
Diesen Abschnitt erweitern, sobald Entscheidungen dazu getroffen sind.

### Grundsatzentscheidungen

- **Baukasten:** vereina besteht aus einem **festen Kern** (Vereinsprofil, Personen und Gruppen,
  Rollen und Rechte, Benachrichtigungen, Aufgaben und Erinnerungen, Dateiablage,
  Datenschutz-Grundlagen) und **wählbaren Modulen**. Vereine schalten ganze Module an oder ab,
  auf Vereins- und auf Abteilungsebene. Details: [Baukasten-Konzept](docs/plans/2026-11-05-baukasten-konzept.md).
- **Architekturregel:** Module sprechen nur über den Kern miteinander und greifen nie direkt auf
  die Daten anderer Module zu. Jedes Modul muss auch ohne die anderen funktionieren.
- **Plugin-System für Module von Dritten:** bewusst auf später verschoben. Die Architekturregel
  hält diese Option offen.

### Wichtige Dokumente

Vor Arbeiten an Konzept oder Umsetzung lesen:

- [Anforderungen](docs/plans/2026-11-05-anforderungen-vereina.md): Leitprinzipien, Anforderungen
  mit Kennungen (z. B. `MIT-01`), Ausbaustufen, offene Entscheidungen
- [Baukasten-Konzept](docs/plans/2026-11-05-baukasten-konzept.md): Kern, Modulkatalog (`M1`–`M17`),
  Abhängigkeiten

Neue Anforderungen bekommen eine Kennung im Anforderungsdokument und werden im Baukasten-Konzept
dem Kern oder einem Modul zugeordnet.

## Dokumentation und Recherchen

**Alle Recherchen und Dokumentationen gehören in den Ordner [`docs/`](docs/).** Keine
Dokumentationsdateien im Wurzelverzeichnis oder verstreut im Code ablegen (Ausnahmen:
`README.md` und `CLAUDE.md`).

Aktuelle Unterteilung:

| Ordner           | Inhalt                                                               |
| ---------------- | -------------------------------------------------------------------- |
| `docs/research/` | Recherchen: Vereinsabläufe, bestehende Lösungen, Technologien         |
| `docs/plans/`    | Anforderungen, Konzepte, Pläne, Umsetzungsschritte und getroffene Entscheidungen |

Regeln:

- Neue Dokumente in den passenden Unterordner legen. Passt keiner, einen neuen, sprechend
  benannten Unterordner in `docs/` anlegen und ihn in dieser Tabelle ergänzen.
- Keine README.md-Dateien in `docs/` oder dessen Unterordnern anlegen – die Tabelle hier
  genügt als Übersicht.
- Dateinamen: `YYYY-MM-DD-kurzes-thema.md` (Kleinbuchstaben, Bindestriche), z. B.
  `2026-11-05-bestehende-vereinssoftware.md`.
- Dokumente auf Deutsch verfassen, im Markdown-Format.
- Recherchen mit Quellenangaben versehen.

## Sprache

Kommunikation und Dokumentation erfolgen auf Deutsch.
