# Integration · Microsoft 365 / Outlook (Microsoft Graph)

> Konkrete Anbindung, damit das
> [Outreach-Modul](../01-software-konzept/08-outreach-und-protokoll-modul.md)
> E-Mails **aus deinem M365-Postfach** versendet, **Antworten liest** und sie
> **automatisch ins Protokoll** schreibt. Stand: Juni 2026.

## Welcher Weg für dich? → Delegierte Berechtigungen

Es gibt zwei Modelle. Für „aus **meinem eigenen** Account senden" ist das erste
richtig:

| Modell | Was es tut | Für dich? |
|---|---|---|
| **Delegiert** (im Namen des angemeldeten Nutzers) | Sendet/liest **nur dein eigenes** Postfach, nach einmaliger Anmeldung | ✅ **Empfohlen** |
| **Application** (App-only, Daemon) | Kann **jedes** Postfach im Tenant — sehr mächtig, muss per *Application Access Policy* / RBAC for Applications auf ein Postfach eingeschränkt werden, braucht Admin | Nur wenn vollautomatisch ohne Login nötig |

Delegiert ist sicherer (kein Zugriff auf fremde Postfächer) und reicht für eine
Einzelperson, die aus ihrem Account heraus Outreach betreibt.[^msdocs-sendmail][^office365itpros]

## Schritt-für-Schritt-Einrichtung

### 1. App-Registrierung (Microsoft Entra ID / Azure AD)
1. Portal → **Microsoft Entra ID → App-Registrierungen → Neue Registrierung**.
2. Name z. B. `Venture-Lens-Outreach`.
3. Kontotypen: „Nur dieser Organisation" (Single-Tenant) genügt.
4. **Redirect-URI** je nach Client (z. B. `http://localhost` für Desktop/Script
   oder deine Web-App-URL).
5. Notieren: **Application (client) ID** und **Directory (tenant) ID**.

### 2. Authentifizierung
- **Client-Secret** anlegen (Zertifikate & Geheimnisse) — Wert sofort sichern,
  er wird nur einmal angezeigt. (Alternativ Zertifikat.)
- Auth-Flow: **OAuth 2.0 Authorization Code** (mit Login) für delegiert.

### 3. API-Berechtigungen (Microsoft Graph → Delegiert)
| Berechtigung | Wofür |
|---|---|
| `Mail.Send` | E-Mails aus deinem Postfach senden |
| `Mail.Read` | Antworten/Posteingang lesen |
| `Mail.ReadWrite` | Status setzen, Ordner/Kategorien verwalten (optional) |
| `offline_access` | Refresh-Token (kein ständiges Neu-Anmelden) |
| `User.Read` | Profil/Account-Identität |

→ „**Administratorzustimmung erteilen**" klicken (oder durch Admin freigeben).

## Senden — `POST /me/sendMail`

```http
POST https://graph.microsoft.com/v1.0/me/sendMail
Authorization: Bearer {access_token}
Content-Type: application/json

{
  "message": {
    "subject": "Anfrage QNG-Zertifizierung Neubau MFH im Raum Köln",
    "body": { "contentType": "Text", "content": "Sehr geehrte Damen und Herren, ..." },
    "toRecipients": [ { "emailAddress": { "address": "anbieter@example.de" } } ]
  },
  "saveToSentItems": true
}
```

Der Body wird aus den [E-Mail-Vorlagen](../templates/email/) mit gefüllten
Platzhaltern erzeugt. Antwort `202 Accepted` = versendet.[^msdocs-sendmail]

## Antworten lesen & zuordnen

- **Abrufen:** `GET /me/mailFolders('inbox')/messages?$select=subject,from,receivedDateTime,bodyPreview,conversationId,internetMessageId`
- **Reply-Zuordnung:** Antworten tragen dieselbe **`conversationId`** wie die
  gesendete Mail → so wird die Antwort automatisch der richtigen Anfrage
  (Anbieter X / Interviewpartner Y) zugeordnet.
- **Verdichten:** Der Antworttext wird strukturiert (Preis, Turnaround, Response
  Time …) und ins Protokoll geschrieben. **Original-Mail bleibt der Beleg
  (Stufe A)**, die LLM-Verdichtung referenziert sie nur (siehe
  [Evidenz-Konzept](../01-software-konzept/04-evidenz-und-datenquellen.md)).

## Echtzeit statt Pollen (optional) — Webhook-Subscription

Für „sofort bei neuer Antwort reagieren":

```http
POST https://graph.microsoft.com/v1.0/subscriptions
{
  "changeType": "created",
  "notificationUrl": "https://<deine-öffentliche-https-url>/graph-webhook",
  "resource": "me/mailFolders('inbox')/messages",
  "expirationDateTime": "2026-06-30T18:00:00Z",
  "clientState": "<geheimes-token>"
}
```

Voraussetzungen: **öffentlich erreichbarer HTTPS-Endpunkt**, Validierung durch
Graph, Subscription muss vor Ablauf **verlängert** werden.[^msdocs-subscription]
Ohne Webhook funktioniert alles auch per regelmäßigem Abruf (Polling).

## Grenzen, Sicherheit & DSGVO
- **Throttling:** Graph hat Sende-/Abruf-Limits — Outreach in Batches, mit Pausen.
- **Secrets** sicher ablegen (Key Vault / Secret-Store), niemals im Repo.
- **DSGVO:** bei Interviews Einwilligung einholen; Antworten nur zweckgebunden für
  die Analyse speichern; Aufbewahrung/Löschung regeln.
- **Least Privilege:** nur die oben genannten delegierten Scopes, nichts darüber.

## Was ich von dir brauche, um es scharf zu schalten
1. **Tenant ID** + **Client ID** der App-Registrierung (keine Secrets im Chat/Repo!).
2. Bestätigung, dass die delegierten Berechtigungen **Admin-Consent** haben.
3. Den **Client-Typ** (Skript/Desktop vs. Web-App) → bestimmt Redirect-URI & Token-Handling.
4. Für Webhooks: eine **öffentliche HTTPS-URL** (sonst nutzen wir Polling).

> Hinweis: In dieser Doku-Umgebung selbst läuft kein Graph-Client — die Anbindung
> wird in der späteren App-/MVP-Stufe ([Roadmap Stufe 1–2](../01-software-konzept/06-roadmap-der-software.md))
> oder einem kleinen Connector-Skript umgesetzt. Diese Anleitung ist die
> vollständige Bauvorlage dafür.

---

### Quellen
[^msdocs-sendmail]: Microsoft Learn, „user: sendMail (Graph v1.0)". https://learn.microsoft.com/en-us/graph/api/user-sendmail?view=graph-rest-1.0
[^msdocs-subscription]: Microsoft Learn, „Create subscription / Receive change notifications through webhooks". https://learn.microsoft.com/en-us/graph/change-notifications-delivery-webhooks
[^office365itpros]: Office 365 for IT Pros, „Control Graph Mail.Send Permission with RBAC for Applications" (Delegated vs. Application, Access Policies). https://office365itpros.com/2026/02/17/mail-send-rbac-for-applications/
