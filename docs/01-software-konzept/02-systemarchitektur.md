# 02 · Systemarchitektur & Module

## Überblick

Venture Lens ist als **Pipeline mit gemeinsamer Datenbasis** gedacht: Jede Idee
wandert durch dieselben Phasen (siehe [03 Bewertungs-Framework](03-bewertungs-framework.md)),
und alle Phasen schreiben in ein zentrales Datenmodell. Module sind die
funktionalen Bausteine, die auf dieses Datenmodell zugreifen.

```
                ┌──────────────────────────────────────────────┐
                │                IDEEN-REPOSITORY                │
                │   (alle Ideen, Status, Vergleich, Archiv)      │
                └───────────────────────┬──────────────────────┘
                                        │
        ┌───────────────┬───────────────┼───────────────┬───────────────┐
        ▼               ▼               ▼               ▼               ▼
 ┌────────────┐ ┌──────────────┐ ┌────────────┐ ┌────────────┐ ┌──────────────┐
 │  IDEE-     │ │  RECHERCHE-  │ │  BUSINESS- │ │  CAPABILITY│ │ IMPLEMENT.-  │
 │  CANVAS    │ │  WORKSPACE   │ │  CASE-CALC │ │  -MODELL   │ │  PLANNER     │
 │ (Phase 1)  │ │ (Phase 2)    │ │ (Phase 3)  │ │ (Phase 4)  │ │ (Phase 6)    │
 └────────────┘ └──────────────┘ └────────────┘ └────────────┘ └──────────────┘
        │               │               │               │               │
        └───────────────┴───────┬───────┴───────────────┴───────────────┘
                                 ▼
              ┌───────────────────────────────────────┐
              │   QUERSCHNITTS-DIENSTE                  │
              │   • Evidenz-Engine (Quellenqualität)    │
              │   • Annahmen-Register                   │
              │   • Scoring- & Entscheidungs-Engine     │
              │   • Report-Generator                    │
              │   • Cadence-/Projekt-Tracker            │
              └───────────────────────────────────────┘
```

## Module (Phasen-Module)

### M1 · Ideen-Repository
Zentrale Liste aller Ideen mit Status (`Rohidee → in Aufbereitung → in
Validierung → Entscheidung → Umsetzung / Archiviert`). Erlaubt **Portfolio-Sicht**:
mehrere Ideen nebeneinander vergleichen (z. B. QNG vs. andere Adjacencies).

### M2 · Idee-Canvas (Phase 1 — Aufbereitung)
Strukturierte Erfassung *pro Idee und pro Variante*:
- Laienverständliche Beschreibung („Erkläre es einem Bauherrn in 3 Sätzen")
- Problem / Zielgruppe / Nutzenversprechen
- **Vor-/Nachteile je Variante** (Pflichtfeld)
- Strategische Passung / Adjacency-Hypothese

### M3 · Recherche-Workspace (Phase 2 — Informations- & Sachlagenfindung)
Arbeitsfläche für alle Recherche-Artefakte: Marktdaten, Wettbewerber, Interviews,
Mystery-Shopping. Jedes Artefakt trägt **Quelle + Evidenz-Stufe** (siehe Modul Q1).

### M4 · Business-Case-Calculator (Phase 3)
Rechenmodell für Pricing, Unit Economics, Szenarien (conservative/base/aggressive),
CAC, Cross-Sell. Inputs sind verlinkte Annahmen aus dem Annahmen-Register.

### M5 · Capability-Modell (Phase 4)
Erfasst benötigte Fähigkeiten/Ressourcen und vergleicht **Build / Hire / Partner**
strukturiert (Kosten, Zeit, Risiko, Kontrolle).

### M6 · Implementation-Planner (Phase 6 — Umsetzung)
90-Tage-/12-Monats-Plan, kritischer Pfad, Abhängigkeiten, CAPEX/OPEX,
Break-even, Risiko-Register. Wandelt einen „Go" in ein Backlog.

## Querschnitts-Dienste

### Q1 · Evidenz-Engine
Bewertet jede Information nach Quellen-Qualität (Stufen A–D, siehe
[04 Evidenz](04-evidenz-und-datenquellen.md)). **Sperrt** Aussagen der Stufe D
(z. B. unbelegte LLM-Ausgaben) für die Entscheidungslogik.

### Q2 · Annahmen-Register
Single Source of Truth für jede Annahme: Wert, Quelle, Evidenz-Stufe,
Unsicherheit, Eigentümer, „validiert/offen". Business Case und Scoring ziehen
ausschließlich hier verlinkte Werte.

### Q3 · Scoring- & Entscheidungs-Engine
Aggregiert Phasen-Ergebnisse zu einem nachvollziehbaren Score und einer
Go/No-Go-Empfehlung (siehe [05 Scoring](05-scoring-und-entscheidung.md)).

### Q4 · Report-Generator
Erzeugt die „harten Outputs" aus den strukturierten Daten:
Wettbewerbsmatrix, Marktdaten-Modell, Konzept (15–25 S.),
Executive-Slides, 1-Pager Go/No-Go, Folgeprojekt-Scope.

### Q5 · Cadence-/Projekt-Tracker
Meilensteine, Wochenrhythmus, schriftliche Status-Updates (Geschafft / Blocker /
Next). Bildet die Projektsteuerung ab (siehe QNG-Übersicht).

## Datenmodell (Kern-Entitäten)

```
Idea
 ├─ id, title, status, owner, created_at
 ├─ strategic_hypothesis
 └─ Variants[]                       (Geschäftsmodell-Optionen)
       ├─ name (z. B. "Plattform", "Eigener Auditor", "Drittanbieter")
       ├─ plain_description
       ├─ pros[] / cons[]
       └─ fit_score

Hypothesis        → was muss wahr sein, damit die Idee trägt
ResearchItem      → finding, source, evidence_grade (A–D), date, method
Assumption        → key, value, unit, source_ref, evidence_grade, confidence, status
Scenario          → name (conservative/base/aggressive), inputs[] → revenue/margin/breakeven
CapabilityOption  → model (build/hire/partner), cost, time, risk, control, pros/cons
Score             → dimension, weight, value, rationale
Decision          → recommendation (go/no-go/conditional), chosen_variant, rationale
ImplementationItem→ task, owner, start/end, dependencies[], capex/opex, risk_ref
Risk              → description, likelihood, impact, mitigation, owner
```

**Verkettung (Traceability):** `Decision` referenziert `Score` → `Assumption` →
`ResearchItem` → `source`. So ist jede Empfehlung bis zur Originalquelle
rückverfolgbar.

## Technische Umsetzung (Empfehlung für MVP)

Für den Piloten ist **keine Eigenentwicklung** nötig. Empfohlener pragmatischer Start:

| Baustein | MVP-Werkzeug | Später (Skalierung) |
|---|---|---|
| Ideen-Repository / Tracker | Airtable / Notion-DB | Eigene Web-App (DB + API) |
| Recherche-Workspace | Notion + Quellen-Tags | Strukturierte DB mit Evidenz-Feld |
| Wettbewerbsmatrix / Marktmodell | Excel/Airtable (Templates in `docs/templates`) | Live-Daten-Anbindung |
| Business-Case-Calc | Excel mit Szenario-Tabs | Modul in Web-App |
| Report-Generator | Word/PPTX-Vorlagen + manuell | Auto-Export aus DB |

> Prinzip: **Erst das Framework an QNG beweisen, dann Software-Tiefe nachziehen.**
> Die Roadmap dazu steht in [06](06-roadmap-der-software.md).
