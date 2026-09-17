# DUA Beratung — Website

Statische Landingpage mit Calendly-Terminbuchung. Keine Datenbank, kein Server nötig.

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette Seite (Design, Texte, Animationen, Buchung) |
| `vercel.json` | Konfiguration und Sicherheits-Header für Vercel |
| `README.md` | Diese Anleitung |

## Auf Vercel veröffentlichen

**Variante A — ohne Programmierkenntnisse (empfohlen)**

1. Konto auf [vercel.com](https://vercel.com) anlegen (kostenlos).
2. Auf „Add New…" → „Project" klicken.
3. Den Ordner mit diesen drei Dateien in das Upload-Feld ziehen.
4. „Deploy" klicken. Nach etwa 30 Sekunden ist die Seite unter einer Adresse wie
   `dua-beratung.vercel.app` erreichbar.

**Variante B — über die Kommandozeile**

```bash
npm i -g vercel
cd dua-site
vercel          # Vorschau-Version
vercel --prod   # Live-Version
```

## Eigene Domain verbinden

1. Domain kaufen, z. B. `dua-beratung.de` bei IONOS, Strato oder Namecheap.
2. In Vercel: Projekt → „Settings" → „Domains" → Domain eintragen.
3. Vercel zeigt die nötigen DNS-Einträge an. Diese beim Domain-Anbieter eintragen:
   - `A`-Record für `dua-beratung.de` → `76.76.21.21`
   - `CNAME`-Record für `www` → `cname.vercel-dns.com`
4. Nach 15 Minuten bis wenigen Stunden ist die Domain aktiv. Das HTTPS-Zertifikat
   richtet Vercel automatisch ein.

## Was du selbst anpassen solltest

In `index.html` per Suchen-und-Ersetzen:

- **Calendly-Link** — suche nach `calendly.com/erwinkoka/30min`
- **E-Mail und Telefonnummer** — suche nach `hallo@dua-beratung.de` und `+49 30 000 000 00`
- **Zahlen im Hero** — suche nach `data-count`. Die Werte `900`, `4.9`, `24` und `2`
  nur mit echten Zahlen belegen.
- **Kundenstimmen** — suche nach `<blockquote>`. Nur echte, freigegebene Zitate verwenden.

## Noch zu erledigen

- [ ] Impressum, Datenschutzerklärung und AGB ergänzen (in Deutschland Pflicht).
      Die Links im Footer zeigen auf `/impressum`, `/datenschutz` und `/agb` —
      dafür braucht es je eine weitere HTML-Datei in diesem Ordner.
- [ ] In der Datenschutzerklärung Calendly und Vercel als Dienstleister nennen.
- [ ] Ein Cookie-/Consent-Hinweis kann nötig sein, sobald Tracking hinzukommt.
- [ ] Zahlungen: In Calendly unter dem Event-Typ → „Payment" Stripe oder PayPal
      verbinden (erfordert den Professional-Tarif).
