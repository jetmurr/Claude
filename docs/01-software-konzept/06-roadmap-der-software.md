# 06 · Roadmap der Software

Prinzip: **Erst das Framework an einer echten Idee (QNG) beweisen, dann
Software-Tiefe nachziehen.** Werkzeug folgt Methode, nicht umgekehrt.

## Stufe 0 — Methode (jetzt, parallel zum QNG-Piloten)
Keine Software-Entwicklung. Das Framework lebt in den Dokumenten und Templates
dieses Repos. QNG wird damit komplett durchgespielt.

- **Ziel:** Beweisen, dass das Framework zu einer belastbaren Entscheidung führt.
- **Werkzeuge:** Excel/Airtable (Matrix, Marktmodell), Notion/Word (Konzept),
  PPTX (Slides). Templates liegen unter `docs/templates`.
- **Erfolg:** QNG-Go/No-Go ist getroffen *und* das Framework hat sich als
  praktikabel erwiesen (Lessons Learned dokumentiert).

## Stufe 1 — MVP (No-Code/Low-Code)
Sobald das Framework steht, wird es in ein leichtes Tool gegossen — ohne
Eigenentwicklung.

- **Ideen-Repository + Tracker** in Airtable/Notion (Status, Portfolio-Sicht).
- **Annahmen-Register** als verknüpfte Tabelle (Wert, Quelle, Evidenz-Stufe).
- **Templates** als wiederverwendbare Vorlagen verlinkt.
- **Scoring** als Tabellen-Formel (Dimensionen × Gewichte).
- **Erfolg:** Eine zweite Idee lässt sich in < 1 Tag aufsetzen.

## Stufe 2 — Strukturierte App
Wenn ≥ 3 Ideen durchgelaufen sind und die Felder stabil sind.

- Eigene Web-App: zentrale DB nach dem Datenmodell aus
  [02 Systemarchitektur](02-systemarchitektur.md).
- **Evidenz-Engine** erzwingt Quellen-/Stufen-Pflicht (sperrt Stufe D).
- **Business-Case-Calculator** als Modul mit Szenarien.
- **Report-Generator**: Ein-Klick-Export der harten Outputs.
- **Erfolg:** Traceability (Decision → Quelle) ist im Tool durchklickbar.

## Stufe 3 — Assistenz & Daten-Anbindung
Optional, wenn Volumen es rechtfertigt.

- Halbautomatische Recherche-Helfer (Quellen vorschlagen, Search-Volume ziehen) —
  **immer mit Evidenz-Stufung**, nie als ungeprüfte Faktenquelle.
- Live-Anbindung amtlicher Datenquellen (Destatis/KfW-Kennzahlen).
- LLM-Assistenz strikt in den drei erlaubten Rollen (strukturieren, Hypothesen,
  aufbereiten) — siehe [04 Evidenz](04-evidenz-und-datenquellen.md).

## Leitplanken über alle Stufen

- **Kein Feature, das die Evidenz-Disziplin aufweicht.** Bequemlichkeit darf nie
  unbelegte Zahlen ins „Go" lassen.
- **Jede Stufe muss eine echte Entscheidung erleichtern**, nicht nur Daten sammeln.
- **Templates bleiben die Quelle der Wahrheit für die Methode** — die App
  digitalisiert sie, ersetzt aber nicht das Denken.
