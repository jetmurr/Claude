# Template · Annahmen-Register

> Single Source of Truth für jede Annahme. Business Case und Scoring ziehen
> **ausschließlich** hier verlinkte Werte. Macht die Empfehlung rückverfolgbar.

## Spalten

| Feld | Beschreibung |
|---|---|
| ID | A-001, A-002 … (zum Verlinken) |
| Annahme | Aussage in einem Satz |
| Wert | Zahl/Range + Einheit |
| Quelle | Link/Referenz |
| Evidenz-Stufe | A / B / C / D |
| Confidence | niedrig / mittel / hoch |
| Status | offen / validiert / widerlegt |
| Eigentümer | wer validiert |
| Auswirkung | Welche Phase/Kennzahl hängt daran? |

## Beispiel-Zeilen (QNG, alle noch offen)

| ID | Annahme | Wert | Quelle | Stufe | Confidence | Status | Owner | Auswirkung |
|---|---|---|---|---|---|---|---|---|
| A-001 | Neubau-Wohnungen p. a. (Marktbasis) | `[ ]` | Destatis | A | – | offen | | TAM |
| A-002 | Anteil QNG-relevant am Neubau | `[ ]` | BMWSB | A | – | offen | | SAM |
| A-003 | Ø Zertifizierungspreis je Projekt | `[ ]` | Mystery Shopping | A | – | offen | | Pricing/Umsatz |
| A-004 | Marge je Vorgang (Variante B) | `[ ]` | abgeleitet | A | – | offen | | Unit Economics |
| A-005 | Conversion RNDG-Bestand → QNG | `[ ]` | eigenes CRM | A | – | offen | | CAC/Cross-Sell |
| A-006 | §7b bleibt über Planungshorizont gültig | `[ ]` | EStG/BMF | A | – | offen | | Risiko R1 |
| A-007 | Auditor-Qualifikation Dauer/Kosten | 6–12 Mon. / 5–15k € | Systemträger | B | – | offen | | Capability/CAPEX |

## Regeln
- **Keine Annahme ohne ID** darf in Business Case/Scoring referenziert werden.
- Eine Annahme der Stufe **D** ist im Scoring **gesperrt** (siehe Evidenz-Doku).
- Beim Validieren: Status auf „validiert" + Quelle + Datum; sonst bleibt „offen".
- **Confidence des Gesamtprojekts** = Anteil „validiert" an entscheidungs­kritischen
  Annahmen (fließt in die Scoring-Confidence ein).
