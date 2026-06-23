# Ideen-Index — Registry aller Business-Ideen

> Zentrale Liste aller Ideen in der Plattform. Jede Idee ist eine Unterkategorie
> mit eigenem Analyse-Workspace nach demselben
> [Bewertungs-Framework](docs/01-software-konzept/03-bewertungs-framework.md).
> Konzept der Hierarchie: [Plattform & Ideenverwaltung](docs/01-software-konzept/07-plattform-und-ideenverwaltung.md).

## Portfolio-Übersicht

| ID | Idee | Status | Score | Confidence | Workspace |
|---|---|---|---|---|---|
| **001** | **QNG-Zertifizierung** (Baubranche) | In Validierung | – (offen) | – | [→ Workspace](docs/02-anwendungsfall-qng/00-uebersicht.md) |
| 002 | *(frei)* | – | – | – | – |
| 003 | *(frei)* | – | – | – | – |

Status-Werte: `Rohidee · In Aufbereitung · In Validierung · Entscheidung ·
Umsetzung · Live · Archiviert`.

---

## Vorlage für eine neue Idee

Beim Anlegen einer Idee diesen Block kopieren und einen Workspace
`docs/0X-anwendungsfall-<name>/` mit den Phasen-Dokumenten 00–08 anlegen
(Struktur analog zu QNG).

```
ID:                    0XX
Titel:
Owner:
Strategische Hypothese:    (Warum passt diese Idee zu uns? Was ist der Adjacency-Move?)
Status:                Rohidee
Erstellt:              YYYY-MM-DD

Phasen-Workspace:
  01 Idee aufbereitet       (Varianten + Vor-/Nachteile)   — Pflicht zuerst
  02 Wettbewerb             (Sachlage A)
  03 Markt                  (Sachlage B)
  04 Business Case
  05 Capability
  06 Umsetzung
  07 Empfehlung (Go/No-Go)
  08 Quellen & Belege
Outreach:                  E-Mail-Vorlagen + Protokolle (docs/templates/email/)
```

> Prinzip: **Methode bleibt identisch, Inhalte je Idee getrennt.** Verbesserungen
> am Framework wirken automatisch für alle Ideen.
