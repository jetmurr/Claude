# Template · Marktdaten-Modell

> Als **Excel** führen. Zweck: adressierbaren Markt (TAM/SAM/SOM) und
> Wachstumskorridor herleiten — **jede Zahl mit Quelle und Stufe**.

## Blatt 1 — Rohdaten (mit Quelle)

| Kennzahl | Wert | Jahr | Quelle | Stufe |
|---|---|---|---|---|
| Fertiggestellte Wohnungen Neubau p. a. | `[ ]` | | Destatis | A |
| Baugenehmigungen Wohngebäude p. a. | `[ ]` | | Destatis | A |
| KfW-KFN-Zusagen (mit QNG) | `[ ]` | | KfW/BMWSB | A |
| Anteil QNG-zertifiziert am Neubau | `[ ]` | | BMWSB | A |
| Ø Zertifizierungskosten / Projekt | `[ ]` | | Mystery Shopping | A |

## Blatt 2 — Marktgrößen (abgeleitet)

| Größe | Formel | Wert |
|---|---|---|
| **TAM** (Total) | Neubau-Projekte p. a. × Ø Zertifizierungspreis | `[ ]` |
| **SAM** (Serviceable) | TAM × realistischer QNG-relevanter Anteil | `[ ]` |
| **SOM** (Obtainable) | SAM × erreichbarer Marktanteil (begründet) | `[ ]` |

> Jede Annahme (Anteile, Marktanteil) verlinkt ins
> [Annahmen-Register](annahmen-register.md).

## Blatt 3 — Wachstumskorridor 2026–2030

| Jahr | Conservative | Base | Aggressive | Treiber/Quelle |
|---|---|---|---|---|
| 2026 | `[ ]` | `[ ]` | `[ ]` | BBSR/BMWSB/KfW |
| … | | | | |
| 2030 | `[ ]` | `[ ]` | `[ ]` | |

Treiber dokumentieren: Neubautrend, Förderpolitik, EU-/nationale Regulatorik,
§7b-Status. **Spannbreite statt Punktprognose.**

## Blatt 4 — Search-Volume (Nachfrage-Indikator)

| Keyword | Volumen/Monat | Trend | Tool | Stufe |
|---|---|---|---|---|
| QNG Auditor | `[ ]` | | Sistrix/Ahrefs | B |
| QNG Zertifizierung | `[ ]` | | | B |
| … | | | | |

## Regeln
- Kein Punktwert ohne Quelle. Fehlt die Quelle → Feld bleibt leer + To-do.
- Prognosen immer als Korridor (3 Szenarien), nie als eine Zahl.
- GPT-/Schätzwerte sind unzulässig (Stufe D, gesperrt).
