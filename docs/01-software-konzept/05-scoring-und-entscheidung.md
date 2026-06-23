# 05 · Scoring & Go/No-Go

Ziel: aus strukturierten Daten eine **nachvollziehbare** Empfehlung machen — so,
dass zwei Personen mit gleichem Datenstand zur gleichen Logik kommen.

## Bewertungsdimensionen

Sechs Dimensionen, jeweils 1–5 bewertet, mit Gewicht. Gewichte sind je Idee
anpassbar (Default unten). Jede Bewertung braucht eine **Begründung mit Quelle**.

| # | Dimension | Frage | Default-Gewicht |
|---|---|---|---|
| 1 | **Marktattraktivität** | Groß genug, wachsend? | 20 % |
| 2 | **Wettbewerbslücke** | Gibt es eine Position, die wir besetzen können? | 15 % |
| 3 | **Nachfrage-Evidenz** | Wollen Kunden das nachweislich (Interviews, Search)? | 20 % |
| 4 | **Wirtschaftlichkeit** | Tragen Marge & Unit Economics? | 20 % |
| 5 | **Machbarkeit / Capability** | Können wir es operativ leisten? | 15 % |
| 6 | **Strategischer Fit** | Passt es zu Portfolio & Cross-Sell? | 10 % |

**Gesamt-Score** = Σ (Dimensionswert × Gewicht), normiert auf 0–100.

## Evidenz-Gate (vor dem Scoring)

Das Scoring ist **nur gültig**, wenn das Evidenz-Gate steht:

- Keine Dimension stützt sich auf Stufe-D-Daten.
- Dimensionen 1, 3, 4 (Markt, Nachfrage, Wirtschaftlichkeit) erreichen mind. Stufe B.

Ist das Gate nicht erfüllt → Status **„Entscheidung vertagt: Datenlücke"**,
nicht „No-Go". Das verhindert, dass fehlende Daten als negatives Signal
fehlinterpretiert werden.

## Confidence-Korrektur

Neben dem Score wird eine **Confidence** (niedrig/mittel/hoch) geführt — abgeleitet
aus dem Anteil der Annahmen, die validiert (nicht offen) sind. Ein hoher Score bei
niedriger Confidence führt zu **Conditional-Go**, nicht zu Go.

## Entscheidungslogik

| Score | Confidence | Empfehlung |
|---|---|---|
| ≥ 70 | hoch | **Go** |
| ≥ 70 | mittel/niedrig | **Conditional-Go** (mit zu schließenden Lücken) |
| 50–69 | beliebig | **Conditional-Go** oder weitere Validierung |
| < 50 | beliebig | **No-Go** (archivieren mit Begründung) |
| beliebig | Evidenz-Gate offen | **Vertagt: Datenlücke** |

> Die Schwellen sind Default-Werte und vor dem ersten Lauf je Idee zu bestätigen,
> damit sie nicht nachträglich „passend gemacht" werden.

## K.-o.-Kriterien (überstimmen den Score)

Bestimmte Befunde führen unabhängig vom Score zu No-Go bzw. Conditional-Go:

- **Regulatorisches K.-o.:** Geschäftsmodell hängt an einer Förder-/Steuerregel,
  die nachweislich kurzfristig ausläuft (z. B. §7b-Sunset) — ohne Plan B.
- **Capability-K.-o.:** Kritische Ressource (z. B. akkreditierter Auditor) ist
  in der geforderten Zeit nicht beschaffbar — in keinem der drei Modelle.
- **Unit-Economics-K.-o.:** Selbst der Base-Case ist strukturell defizitär.

## Output der Entscheidung

Das Ergebnis ist immer ein **1-Pager**:

1. Empfehlung (Go / Conditional-Go / No-Go / Vertagt) — ein Satz.
2. Score-Tabelle (6 Dimensionen, Wert, Gewicht, Begründung+Quelle).
3. Confidence + größte offene Annahmen.
4. Bei Go: empfohlenes Betriebsmodell + Folgeprojekt-Scope.
5. Bei No-Go: Begründung + Bedingung, unter der die Idee zu reaktivieren ist.
