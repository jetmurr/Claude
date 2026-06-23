# 08 · Outreach- & Protokoll-Modul (E-Mail-Ansprache + Auto-Protokoll)

> Anforderung: Die Software soll **Menschen per E-Mail ansprechen** (Mystery
> Shopping, Customer Interviews, Partner), die Mails **aus deinem E-Mail-Account**
> versenden, **Antworten einlesen** und sie **als Protokoll** in die jeweilige
> Idee aufnehmen.

## Was das Modul leisten soll (Workflow)

```
 1 Vorlage wählen      →  2 Personalisieren  →  3 Versand (dein Account)
        ▲                                                │
        │                                                ▼
 6 Auto-Protokoll  ←  5 Antwort verdichten  ←  4 Antwort-Eingang/Tracking
   (in Idee +                (LLM strukturiert,         (Reply-Erkennung,
    Matrix/Register)          Quelle bleibt Original)    Status: gesendet/
                                                         geantwortet/Nachfass)
```

1. **Vorlage wählen** — aus der Template-Bibliothek (z. B. Mystery-Shopping-Anfrage,
   Interview-Einladung, Partner-Ansprache) → [E-Mail-Vorlagen](../templates/email/).
2. **Personalisieren** — Platzhalter (`{{Anbieter}}`, `{{Projektgröße}}` …) füllen,
   **identisches Briefing** bei Mystery Shopping erzwingen (Vergleichbarkeit).
3. **Versand aus deinem Account** — die Mail geht über *deine* Adresse raus (nicht
   über eine fremde), damit Antworten bei dir landen und der Absender vertraut wirkt.
4. **Eingang & Tracking** — eingehende Antworten werden der Anfrage zugeordnet;
   Status je Kontakt (gesendet / geöffnet / geantwortet / Nachfass fällig).
5. **Antwort verdichten** — der Antworttext wird strukturiert (Preis, Turnaround,
   Response Time, Aufklärungstiefe …). Der LLM **fasst nur zusammen**; die
   Original-Antwort bleibt als Beleg erhalten.
6. **Auto-Protokoll** — Ergebnis landet automatisch im richtigen Artefakt:
   Mystery Shopping → [Wettbewerbsmatrix](../templates/wettbewerbsmatrix.md);
   Interview → Interview-Register; jeweils mit **Evidenz-Stufe A (dokumentiert)**.

## Evidenz-Disziplin im Outreach

- Die **Original-Antwort** (E-Mail-Text) ist der Beleg → Stufe A.
- Die **LLM-Verdichtung** ist nur Aufbereitung; sie referenziert das Original und
  ist für sich genommen Stufe D (siehe [04 Evidenz](04-evidenz-und-datenquellen.md)).
- Kein Insight ohne zugeordnete Original-Antwort. „Aus dem Gedächtnis" zählt nicht.

## Technische Anbindung (um *real* zu senden/lesen)

Damit aus deinem Account gesendet und gelesen werden kann, braucht das Modul eine
Postfach-Anbindung. Optionen:

| Variante | Wie | Eignung |
|---|---|---|
| **Microsoft Graph** (OAuth, delegiert) | Microsoft-365-Konto autorisieren | **Outlook/M365 — für dieses Projekt gewählt** ✅ |
| Gmail API (OAuth) | Google-Konto autorisieren | Google-Workspace/Gmail |
| IMAP/SMTP | Server + App-Passwort | beliebiger Anbieter |
| CRM/Tool mit Mailversand | z. B. über bestehendes CRM | wenn schon vorhanden |

→ **Gewählte Anbindung: Microsoft 365.** Vollständige Einrichtungsanleitung
(App-Registrierung, delegierte Berechtigungen `Mail.Send`/`Mail.Read`, `sendMail`,
Reply-Zuordnung via `conversationId`, Webhooks):
**[Microsoft-Graph-E-Mail-Integration](../integrationen/microsoft-graph-email.md)**.

Querschnitt: **DSGVO/Einwilligung** (gerade bei Interviews), Bounce-/Spam-Handling,
Rate-Limits, klare Kennzeichnung als reale Anfrage.

## Wichtig — aktueller Stand & ehrliche Einordnung

> In der **jetzigen Umgebung** (Code-/Dokumenten-Workspace) ist **kein E-Mail-
> Postfach angebunden**. Ich kann hier **nicht** direkt aus deinem Account senden
> oder deinen Posteingang lesen.

**Was jetzt schon nutzbar ist:**
- **Versandfertige E-Mail-Vorlagen** (Deutsch, personalisierbar) → [templates/email/](../templates/email/).
  Du kannst sie sofort kopieren und aus deinem Mailprogramm verschicken.
- **Protokoll-Vorlagen**, in die du Antworten einträgst (oder mir zum Verdichten
  gibst) → [Mystery-Shopping-Protokoll](../templates/mystery-shopping-protokoll.md),
  Interview-Register im [Customer-Interview-Guide](../templates/customer-interview-guide.md).
- **Verdichtung durch mich:** Du kannst mir eingegangene Antworten einfügen — ich
  strukturiere sie regelkonform ins Protokoll und die Matrix.

**Um den vollautomatischen Versand/Einlesen zu aktivieren**, wird die
**Microsoft-Graph-Anbindung** eingerichtet (delegiert, eigenes Postfach) — die
vollständige Bauvorlage steht unter
[Microsoft-Graph-E-Mail-Integration](../integrationen/microsoft-graph-email.md).
Sobald App-Registrierung + Admin-Consent stehen, läuft der Workflow oben
End-to-End.
