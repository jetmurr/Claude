# 04 · Evidenz & Datenquellen

> Kernsatz des Qualitätsanspruchs: **Primärdaten > Sekundärdaten. Jede Zahl mit
> Quelle. Keine „ChatGPT-Recherche".** Dieses Dokument macht daraus eine
> verbindliche Mechanik.

## Evidenz-Stufen (A–D)

Jede Information (`ResearchItem`, `Assumption`) trägt eine Stufe. Die Stufe
entscheidet, ob die Information in die Entscheidung einfließen darf.

| Stufe | Bedeutung | Beispiele | In Entscheidung? |
|---|---|---|---|
| **A** | Primär / amtlich / peer-reviewed | Destatis, BMWSB, BBSR, KfW, Gesetzestext, eigene Mystery-Shopping-Transkripte, eigene Interview-Notizen | Ja, voll |
| **B** | Seriöse Sekundärquelle | Branchenverbände (DGNB etc.), Fachverbände, etablierte Marktstudien mit Methodik | Ja |
| **C** | Schwach / interessengeleitet | Anbieter-Eigenangaben, Pressemeldungen, Foren, einzelne Blogposts | Nur als Indiz, markiert |
| **D** | Unbelegt / generiert | **Reine LLM-Ausgabe ohne Quelle**, Hörensagen, Schätzung ohne Herleitung | **Gesperrt** — kein „Go" darauf |

**Regel:** Eine Go-Empfehlung darf sich auf **keine** Aussage der Stufe D stützen.
Kritische Kennzahlen (Marktvolumen, Pricing, Marge) sollen mindestens **Stufe B**,
idealerweise **A** erreichen.

## Rolle von LLMs (inkl. dieser Software)

LLMs dürfen **nur** für drei Dinge eingesetzt werden — nie als Faktenquelle:

1. **Strukturieren** — Rohnotizen ordnen, Fragen formulieren, Texte verständlich machen.
2. **Hypothesen generieren** — die *dann* primär validiert werden müssen.
3. **Aufbereiten** — Zusammenfassen bereits belegter Inhalte.

Jede so entstandene Aussage startet als **Stufe D** und muss durch eine echte
Quelle „hochgestuft" werden, sonst bleibt sie gesperrt.

## Kuratierte Quellenliste (Bau / Nachhaltigkeit / Förderung — relevant für QNG)

| Quelle | Was man dort bekommt | Stufe |
|---|---|---|
| **Destatis** (Statistisches Bundesamt) | Baufertigstellungen, Baugenehmigungen, Wohnungsneubau p. a. | A |
| **BMWSB** | QNG-Regelwerk, Förderlogik, politische Rahmensetzung | A |
| **BBSR** | Bau-/Wohnungsmarkt-Analysen, Prognosen | A |
| **KfW** | Förderprogramme (z. B. Klimafreundlicher Neubau), Antrags-/Zusagezahlen | A |
| **Gesetze (EStG §7b u. a.)** | Sonder-AfA-Bedingungen, Befristungen | A |
| **DGNB / BNB / NaWoh / BiRN** | Akkreditierte Bewertungssysteme, Auditor-Ausbildung, Anbieterlisten | B |
| **Sistrix / Ahrefs** | Search-Volume zu Keywords (Nachfrage-Indikator) | B |
| **Mystery Shopping (eigen)** | Reale Preise, Turnaround, Servicequalität der Wettbewerber | A* |
| **Customer Interviews (eigen)** | Echte Zahlungsbereitschaft, Pains, Entscheidungswege | A* |

\* Eigene Primärerhebungen sind nur Stufe A, wenn sie **dokumentiert** sind
(Transkript/Notizen, Datum, Briefing). Undokumentierte Erinnerung = Stufe C.

## Dokumentationspflicht je Quelltyp

| Quelltyp | Mindest-Dokumentation |
|---|---|
| Statistik / Behörde | Link, Tabellen-/Berichtsname, Stand-Datum, abgerufene Kennzahl |
| Mystery Shopping | Anbieter, Datum, identisches Briefing-Template, Transkript/Notiz, Ergebnis |
| Customer Interview | Rolle/Segment, Datum, Leitfaden, Notiz/Transkript, Kern-Insights |
| Search-Volume | Tool, Keyword, Zeitraum, Wert, Screenshot |

## „Trust but verify"-Checkliste vor jeder Entscheidung

- [ ] Stützt sich die Empfehlung auf eine Stufe-D-Aussage? → **Stoppen.**
- [ ] Hat jede kritische Kennzahl eine Quelle und ein Datum?
- [ ] Sind Mystery Shopping & Interviews dokumentiert (nicht aus dem Gedächtnis)?
- [ ] Ist die Wettbewerbsmatrix strukturiert (Tabelle), nicht Prosa?
- [ ] Sind politische/regulatorische Risiken (z. B. Förder-/AfA-Befristung) explizit?
