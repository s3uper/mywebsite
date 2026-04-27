# README - Persoenliche Webseite

## 1. Projektuebersicht
Dieses Projekt ist meine persoenliche Webseite mit drei Seiten:
- Home ([index.html](index.html))
- Kontakt ([kontakt.html](kontakt.html))
- Lebenslauf ([lebenslauf.html](lebenslauf.html))

Technik-Stack:
- HTML
- CSS
- JavaScript

Es ist eine statische Webseite ohne Framework.

Hosting:
- Cloudflare Pages
- Repo-Anbindung ueber GitHub

## 2. Lokale Entwicklung in VS Code
Ich nutze **Live Server** (Erweiterung von **Ritwick Dey**), um Aenderungen direkt im Browser zu sehen.

### So starte ich Live Server
1. Datei im Projekt oeffnen (z. B. `index.html`)
2. Unten rechts in VS Code auf **Go Live** klicken

### Tastenkombination
```text
Alt+L, Alt+O
```
(Erst `Alt+L`, dann `Alt+O`)

Wenn Live Server laeuft, aktualisiert sich die Seite bei Speichern automatisch.

## 3. Aenderungen veroeffentlichen (Git-Workflow)
Nach Aenderungen im Projektordner im Terminal:

```bash
git add .
git commit -m "Beschreibung der Aenderung"
git push
```

Danach deployed Cloudflare Pages automatisch, meist innerhalb von 1-2 Minuten.

Deployment-Status pruefen:
- Cloudflare Dashboard
- Workers & Pages
- Mein Projekt
- Deployments

## 4. Eigene Domain verbinden
Schritte in Cloudflare:
1. Dashboard oeffnen
2. Pages-Projekt waehlen
3. Tab **Custom domains**
4. **Set up a custom domain** klicken
5. Domain eingeben

Wichtig:
Wenn die Domain noch nicht ueber Cloudflare verwaltet wird, muessen zuerst beim Domain-Anbieter die Nameserver auf die von Cloudflare umgestellt werden.

SSL/HTTPS wird automatisch eingerichtet.

## 5. Test-Branches fuer Aenderungen ohne Live-Going
Wenn ich etwas testen will, ohne direkt live zu gehen:

```bash
git checkout -b test
```

Dann im Test-Branch arbeiten, committen und pushen.
Cloudflare erstellt dafuer automatisch eine Preview-URL.

Erst nach Merge in `main` geht die Aenderung live.

## 6. Haeufige Probleme & Loesungen
### Fehler: "Failed: error occurred while fetching repository"
Loesung:
- GitHub-App-Berechtigung pruefen unter:
  `github.com/settings/installations`

### Aenderungen nicht sichtbar
Loesung:
- Browser hart neu laden mit **Strg+F5**

### Deployment schlaegt fehl
Loesung:
- Logs im Cloudflare-Dashboard pruefen (Deployments)

## 7. Wichtige Dateien im Projekt
- [index.html](index.html) - Startseite
- [kontakt.html](kontakt.html) - Kontaktformular
- [lebenslauf.html](lebenslauf.html) - Lebenslauf
- [s3uper-website.html](s3uper-website.html) - zusaetzliche/alternative Startdatei (falls genutzt)

Wenn spaeter eigene CSS- oder JavaScript-Dateien dazukommen (z. B. `styles.css`, `script.js`), sollten sie hier kurz dokumentiert werden.

---

Kurz-Merksatz:
1. Lokal testen (Live Server)
2. `git add .`, `git commit`, `git push`
3. Deployment in Cloudflare pruefen
4. Erst bei Bedarf in `main` mergen
