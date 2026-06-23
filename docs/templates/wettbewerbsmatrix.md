# Template · Wettbewerbsmatrix

> Als **Excel/Airtable** führen (nicht Prosa). Diese Datei definiert Spalten,
> Bewertungslogik und Befüllungsregeln. Mindestens **15 Anbieter**.

## Tabellenstruktur (Spalten)

| Spalte | Typ | Beschreibung | Quelle/Stufe |
|---|---|---|---|
| Anbieter | Text | Name | — |
| Typ | Auswahl | Auditor / Zertifizierungsstelle / Plattform / LCA-Software / Generalist | — |
| Systemträger | Auswahl | DGNB / BNB / NaWoh / BiRN / mehrere | B |
| Region | Text | Tätigkeitsgebiet | C |
| Leistungsumfang | Text | Was genau angeboten wird | C |
| **Preis** | Zahl/Range | aus Mystery Shopping | A |
| **Turnaround** | Zahl | Zeit bis Angebot / Projektdauer | A |
| **Response Time** | Zahl | Zeit bis erste Reaktion | A |
| **Service-Score** | 1–5 | Beratung/Verständlichkeit | A |
| **Funnel-UX-Score** | 1–5 | Einfachheit Einstieg | A/C |
| **Aufklärungstiefe** | 1–5 | Förder-/§7b-Kontext mitgedacht? | A |
| Quelle/Link | URL | Beleg | — |
| Evidenz-Stufe | A–D | je Zeile | — |
| Notiz | Text | Auffälligkeiten | — |

## Bewertungslogik
- Achsen 1–5, Gewichte je Spalte anpassbar (Default gleichgewichtet).
- **Gesamt-Score je Anbieter** = gewichteter Mittelwert der 1–5-Achsen.
- Anbieter sortierbar nach Score → zeigt Best-in-Class und Lücken.

## Befüllungsregeln
- Preis/Turnaround/Response/Service **nur aus dokumentiertem Mystery Shopping** (A).
- Reine Website-Angaben = Stufe C, als solche markieren.
- Leere Felder bleiben leer (nicht schätzen) — sichtbare Lücke ist ehrlicher.

## Auswertung → Lücken-Analyse
Am Ende drei Fragen beantworten (mit Zeilenbezug):
1. Wo ist das Marktmittel schwach (z. B. Response Time)? → Angriffspunkt.
2. Welche Achse beherrscht niemand (z. B. Aufklärungstiefe)? → Positionierung.
3. Welcher Anbietertyp fehlt ganz? → White Space.
