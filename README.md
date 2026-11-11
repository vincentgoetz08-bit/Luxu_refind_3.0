# luxu_refind.

Onlineshop für geprüfte Designermode aus zweiter Hand von Justus und Janno.

## Aufbau

| Ordner / Datei | Inhalt |
|---|---|
| `index.html` | Der komplette Shop |
| `data/produkte.json` | Alle Produkte (wird über das Portal gepflegt) |
| `data/einstellungen.json` | Versandkosten, Hinweisleiste usw. (über das Portal) |
| `images/produkte/` | Produktfotos (Uploads aus dem Portal landen hier) |
| `images/seite/` | Startbild, Kategoriebilder, Logo |
| `admin/` | Verwaltungsportal (Decap CMS) unter `/admin` |

## Einrichtung (einmalig)

1. **GitHub:** Neues Repository `luxu-refind` anlegen (privat ist möglich) und den Inhalt dieses Ordners hochladen.
2. **Netlify:** „Add new project“ → „Import an existing project“ → GitHub → `luxu-refind`. Build command leer lassen, Publish directory `.` → Deploy. Projekt in `luxu-refind` umbenennen.
3. **GitHub OAuth App:** github.com → Settings → Developer settings → OAuth Apps → New OAuth App
   - Homepage URL: `https://luxu-refind.netlify.app`
   - Authorization callback URL: `https://api.netlify.com/auth/done`
   - Danach Client ID kopieren und ein Client Secret erzeugen.
4. **Netlify:** Project configuration → Access & security → OAuth → Install provider → GitHub → Client ID und Secret eintragen.
5. **admin/config.yml:** Bei `repo:` den eigenen GitHub-Namen eintragen, z. B. `vincent-goetz/luxu-refind`.
6. **Zugriff für Justus und Janno:** Repository → Settings → Collaborators → Add people. Beide brauchen ein eigenes GitHub-Konto und müssen die Einladung annehmen.

## Produkte pflegen

1. `https://luxu-refind.netlify.app/admin` öffnen und „Mit GitHub einloggen“.
2. „Shop“ → „Produkte“ → „Produkt hinzufügen“, Felder ausfüllen, Fotos hochladen.
3. Oben auf „Veröffentlichen“ klicken. Nach etwa einer Minute ist die Änderung im Shop sichtbar.
4. Verkaufte Teile: Schalter „Verkauft“ einschalten. Das Teil verschwindet aus dem Shop.

Nur GitHub-Konten mit Schreibzugriff auf das Repository können sich im Portal anmelden.

## Vor dem echten Start

- Impressum, Datenschutz, AGB und Widerrufsbelehrung eintragen (Platzhalter in `index.html`).
- Bezahlung einrichten (Platzhalter auf der Kassenseite).
- In `index.html` die Zeile `<meta name="robots" content="noindex, nofollow">` entfernen und in `robots.txt` `Disallow: /` durch `Allow: /` ersetzen, damit Google den Shop findet.
- Platzhalterfotos durch eigene Fotos ersetzen.
