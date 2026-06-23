# QNG · 00 Übersicht & Projektsteuerung

> Erster konkreter Anwendungsfall des Venture-Lens-Frameworks. Dies ist die
> 1:1-Übersetzung deines Leitfadens in die Phasenlogik der Software.

## Projektziel (das WARUM)

Fundierte Entscheidungsgrundlage, ob **Gutachten.org** QNG-Zertifizierungen ins
Portfolio aufnimmt. Output ist eine **Go/No-Go-Empfehlung** mit
Geschäftsmodell-Konzept und 90-Tage-Implementierungsplan — **kein
Wikipedia-Artikel über QNG**.

**Strategische Hypothese (zu validieren):** QNG ist ein logischer
Adjacency-Move von Altbau-RNDG zu Neubau-Sonder-AfA (§7b EStG) und erweitert das
steuerliche Optimierungsportfolio von Bestand auf Neubau.

## Scope — sechs Pflicht-Deliverables (↔ Framework-Phasen)

| Leitfaden | Inhalt | Framework-Phase | Dokument |
|---|---|---|---|
| A Wettbewerbsanalyse | ≥ 15 Anbieter, Mystery Shopping, Scoring-Matrix | 2 | [02](02-wettbewerbsanalyse.md) |
| B Marktnachfrage | Volumen, Wachstum, Search-Volume, Discovery, §7b-Risiko | 2 | [03](03-marktnachfrage.md) |
| C Business Case | Pricing, Unit Economics, 3 Szenarien, Cross-Sell, CAC | 3 | [04](04-business-case.md) |
| D Capability | Build/Hire/Partner, Auditor-Realität, Tech | 4 | [05](05-capability-assessment.md) |
| E Roadmap | 90-Tage-Plan, CAPEX/OPEX, Break-even, Risiken | 6 | [06](06-implementation-roadmap.md) |
| F Recommendation | Go/No-Go, Modellwahl, Folgeprojekt-Scope | 5 | [07](07-empfehlung-go-no-go.md) |

Zusätzlich vorgeschaltet (Framework-Phase 1, vom Nutzer gefordert): die
**verständliche Aufbereitung der Idee** inkl. Geschäftsmodell-Varianten →
[01 Idee aufbereitet](01-idee-aufbereitet.md).

## Out of Scope

Implementierung selbst, tatsächliche Auditor-Ausbildung, Plattform-Entwicklung.
→ Folgeprojekt.

## Qualitätsanspruch (verbindlich)

- **Primärdaten > Sekundärdaten.** Jede Zahl mit Quelle. Bevorzugt Destatis,
  BMWSB, BBSR, KfW, peer-reviewed.
- **Keine „ChatGPT-Recherche".** Nur durch GPT generierte Zahlen sind ungültig
  (Evidenz-Stufe D, gesperrt).
- Mystery Shopping & Interviews mit **Transkript/Notizen** dokumentiert.
- Wettbewerbsmatrix als **Excel/Airtable**, nicht Prosa.

> Stand in diesem Repo: Markt-/Förder-/Steuer-Eckdaten sind **recherchiert und
> belegt** (siehe [08 Quellen](08-quellen-und-belege.md)). Verbleibende
> Primärdaten (Wettbewerbspreise, Search-Volume, Interviews, CRM-Conversion) sind
> als `[zu erheben]` markiert — mit Quelle und Methode, nicht erfunden.

## Harte Outputs

- Wettbewerbsmatrix (Excel) → Template: [wettbewerbsmatrix](../templates/wettbewerbsmatrix.md)
- Marktdaten-Modell (Excel) → Template: [marktdaten-modell](../templates/marktdaten-modell.md)
- 15–25 Seiten Konzept (Word/PDF)
- 10–15 Slides Executive Summary (PPTX)
- 1-Pager Go/No-Go-Recommendation → [07](07-empfehlung-go-no-go.md)
- Folgeprojekt-Scope (1-Pager) → [07](07-empfehlung-go-no-go.md)

## Cadence & Meilensteine

| Woche | Ziel |
|---|---|
| W1 | Wettbewerbsanalyse + erste Marktdaten |
| W2 | Mystery Shopping abgeschlossen + Business-Case-Draft |
| W3 | Customer Interviews + Capability-Modell |
| W4 | Finales Konzept + Präsentation |

- Wöchentlich 30 min Sync.
- Schriftliches Status-Update **freitags**: Was geschafft / Blocker / Next.

## Erfolgskriterien

Das Projekt ist erfolgreich, wenn:

1. Auf Basis des Outputs eine **Investment-Entscheidung** möglich ist.
2. Die Empfehlung **daten- statt bauchgestützt** ist.
3. Ca. **5 Mystery-Shopping-Insights** so konkret sind, dass sie die
   Positionierung formen.
4. Der **Folgeprojekt-Scope 100 % implementierungsfähig** ist.
