# Venture Lens — Konzept & erster Anwendungsfall QNG

> Arbeitstitel der Software: **Venture Lens** (austauschbar). Interner Kontext: Gutachten.org / Evalion-Portfolio.

Dieses Repository beschreibt **eine Plattform**, in die beliebig viele
Business-Ideen eingepflegt werden. Jede Idee ist eine **Unterkategorie** mit
eigenem Analyse-Workspace nach demselben Framework. **QNG ist Idee 001** — die
erste Unterkategorie.

```
VENTURE LENS  (eine Software)
├── IDEEN-INDEX                 → Registry & Portfolio-Vergleich aller Ideen
├── Idee 001 · QNG             ✅ aktiv, mit belegter Recherche
├── Idee 002 · (frei)
└── …
```

Enthalten sind:

1. **Das Software-Konzept** — wie Ideen von der ersten Eingebung bis zur
   Umsetzungsentscheidung geprüft werden (verständlich aufbereitet, markt­seitig
   durchleuchtet, wirtschaftlich bewertet, Go/No-Go), inkl. **Plattform-/
   Ideenverwaltung** und **Outreach-/E-Mail-Modul**.
2. **Der erste Anwendungsfall QNG** — durchgespielt inkl. Geschäftsmodell-
   Varianten (Plattform / eigener Auditor / Drittanbieter) und **mit echten,
   quellenbelegten Marktdaten** (Destatis, BMWSB, KfW, EStG/BMF, DGNB/BiRN).

→ Start: **[IDEEN-INDEX](IDEEN-INDEX.md)** (alle Ideen) ·
**[QNG-Workspace](docs/02-anwendungsfall-qng/00-uebersicht.md)** (erste Idee).

---

## Leitprinzip

> **Erst verstehen, dann bewerten, dann entscheiden, dann umsetzen.**

Jede Idee durchläuft dieselben Phasen in derselben Reihenfolge. Keine Idee
springt in den Business Case, bevor sie nicht laienverständlich aufbereitet und
in ihren Vor-/Nachteilen klar ist.

---

## Navigation

### Software-Konzept (generisch, wiederverwendbar)
| Dokument | Inhalt |
|---|---|
| [01 Vision & Ziele](docs/01-software-konzept/01-vision-und-ziele.md) | Wofür die Software da ist, was sie *nicht* ist |
| [02 Systemarchitektur & Module](docs/01-software-konzept/02-systemarchitektur.md) | Bausteine, Datenmodell, Workflow |
| [03 Bewertungs-Framework](docs/01-software-konzept/03-bewertungs-framework.md) | Die 7 Phasen von Ideenfindung bis Umsetzung |
| [04 Evidenz & Datenquellen](docs/01-software-konzept/04-evidenz-und-datenquellen.md) | Quellen-Qualitätsstufen, „keine ChatGPT-Recherche" |
| [05 Scoring & Go/No-Go](docs/01-software-konzept/05-scoring-und-entscheidung.md) | Wie aus Daten eine Entscheidung wird |
| [06 Roadmap der Software](docs/01-software-konzept/06-roadmap-der-software.md) | MVP → Ausbaustufen |
| [07 Plattform & Ideenverwaltung](docs/01-software-konzept/07-plattform-und-ideenverwaltung.md) | Eine Software, viele Ideen — Hierarchie & Lebenszyklus |
| [08 Outreach- & Protokoll-Modul](docs/01-software-konzept/08-outreach-und-protokoll-modul.md) | E-Mail-Ansprache aus deinem Account + Auto-Protokoll |

### Anwendungsfall QNG (konkret)
| Dokument | Inhalt |
|---|---|
| [00 Übersicht & Steuerung](docs/02-anwendungsfall-qng/00-uebersicht.md) | Projektziel, Scope, Cadence, Erfolgskriterien |
| [01 Idee aufbereitet](docs/02-anwendungsfall-qng/01-idee-aufbereitet.md) | QNG laienverständlich + Geschäftsmodell-Varianten mit Vor-/Nachteilen |
| [02 Wettbewerbsanalyse](docs/02-anwendungsfall-qng/02-wettbewerbsanalyse.md) | Anbieter-Mapping, Mystery Shopping, Scoring-Matrix |
| [03 Marktnachfrage](docs/02-anwendungsfall-qng/03-marktnachfrage.md) | Marktvolumen, Wachstum, Search-Volume, Customer Discovery |
| [04 Business Case](docs/02-anwendungsfall-qng/04-business-case.md) | Pricing, Unit Economics, Szenarien, Cross-Sell |
| [05 Capability Assessment](docs/02-anwendungsfall-qng/05-capability-assessment.md) | Build / Hire / Partner, Tech, Auditor-Realität |
| [06 Implementation Roadmap](docs/02-anwendungsfall-qng/06-implementation-roadmap.md) | 90-Tage-Plan, CAPEX/OPEX, Break-even, Risiken |
| [07 Empfehlung](docs/02-anwendungsfall-qng/07-empfehlung-go-no-go.md) | Go/No-Go, Modellwahl, Folgeprojekt-Scope |
| [08 Quellen & Belege](docs/02-anwendungsfall-qng/08-quellen-und-belege.md) | Evidenz-Register: alle Quellen mit Stufe |

### Templates (für QNG und jede Folge-Idee)
| Template | Zweck |
|---|---|
| [Wettbewerbsmatrix](docs/templates/wettbewerbsmatrix.md) | Anbieter strukturiert vergleichen |
| [Marktdaten-Modell](docs/templates/marktdaten-modell.md) | Marktvolumen & Prognose, jede Zahl mit Quelle |
| [Annahmen-Register](docs/templates/annahmen-register.md) | Jede Annahme nachvollziehbar & prüfbar |
| [Mystery-Shopping-Protokoll](docs/templates/mystery-shopping-protokoll.md) | Identisches Briefing, dokumentierte Insights |
| [Customer-Interview-Guide](docs/templates/customer-interview-guide.md) | Strukturierte Discovery-Interviews |
| [E-Mail-Vorlagen](docs/templates/email/README.md) | Mystery Shopping, Interview-Einladung, Partner, Nachfass |

---

## Datenehrlichkeit (gilt im ganzen Repo)

Im QNG-Anwendungsfall sind zentrale Fakten **recherchiert und mit Quelle belegt**
(jede mit Evidenz-Stufe) — u. a.:
- QNG seit 2021; **10.000. Wohneinheit im März 2026** ausgezeichnet, ~1.700 Siegel,
  Zahlen stark steigend (BMWSB).
- Neubau-Basismarkt: **251.900 fertiggestellte Wohnungen 2024** (Destatis).
- KfW KFN: Förderkredit **bis 150.000 € mit QNG** statt 100.000 € (KfW).
- **§ 7b EStG befristet — letztmalig VZ 2026**, gekoppelt an EH40 + QNG (EStG/BMF).

→ Vollständige Quellenliste: [QNG/08 Quellen & Belege](docs/02-anwendungsfall-qng/08-quellen-und-belege.md).

**Noch nicht erhobene Primärdaten** (konkrete Wettbewerbspreise, Search-Volume,
Kunden-Interviews, CRM-Conversion) bleiben bewusst als `[zu erheben]` markiert —
inklusive Methode. Das entspricht dem Qualitätsanspruch: *Primärdaten >
Sekundärdaten, jede Zahl mit Quelle, keine reine GPT-Recherche.*
