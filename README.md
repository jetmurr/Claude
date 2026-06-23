# Venture Lens — Konzept & erster Anwendungsfall QNG

> Arbeitstitel der Software: **Venture Lens** (austauschbar). Interner Kontext: Gutachten.org / Evalion-Portfolio.

Dieses Repository enthält **zwei zusammengehörige Dinge**:

1. **Das Konzept einer Software**, die Geschäftsideen systematisch von der ersten
   Idee bis zur Umsetzungsentscheidung prüft — verständlich aufbereitet,
   markt­seitig durchleuchtet, wirtschaftlich bewertet und mit einer klaren
   Go/No-Go-Empfehlung versehen.
2. **Den ersten konkreten Anwendungsfall: QNG** (Qualitätssiegel Nachhaltiges
   Gebäude) — eine reale Geschäftsidee, durch das Framework gespielt, inklusive
   der Geschäftsmodell-Varianten (Plattform / eigener Auditor / Drittanbieter).

Die Idee dahinter: Das Framework wird **einmal sauber gebaut** und danach auf
jede neue Geschäftsidee angewandt. QNG ist der Pilot, an dem das Framework
geschärft wird.

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

### Templates (für QNG und jede Folge-Idee)
| Template | Zweck |
|---|---|
| [Wettbewerbsmatrix](docs/templates/wettbewerbsmatrix.md) | Anbieter strukturiert vergleichen |
| [Marktdaten-Modell](docs/templates/marktdaten-modell.md) | Marktvolumen & Prognose, jede Zahl mit Quelle |
| [Annahmen-Register](docs/templates/annahmen-register.md) | Jede Annahme nachvollziehbar & prüfbar |
| [Mystery-Shopping-Protokoll](docs/templates/mystery-shopping-protokoll.md) | Identisches Briefing, dokumentierte Insights |
| [Customer-Interview-Guide](docs/templates/customer-interview-guide.md) | Strukturierte Discovery-Interviews |

---

## Datenehrlichkeit (gilt im ganzen Repo)

Im QNG-Anwendungsfall sind **belastbare Strukturfakten** ausgearbeitet
(z. B. dass QNG ein staatliches Siegel des BMWSB ist, über DGNB/BNB/NaWoh/BiRN
akkreditiert wird, an KfW-Förderung gekoppelt ist).

**Quantitative Aussagen** (Marktvolumen, Preise, Auditor-Zahlen, Search-Volume)
sind bewusst **nicht erfunden**, sondern als `[zu erheben]` markiert — inklusive
Quelle und Methode. Das entspricht dem Qualitätsanspruch: *Primärdaten >
Sekundärdaten, jede Zahl mit Quelle, keine GPT-Recherche.*
