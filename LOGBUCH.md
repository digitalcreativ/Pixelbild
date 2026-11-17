# Logbuch – Pixelbild-Tool

Online: https://digitalcreativ.github.io/Pixelbild/
Repository: https://github.com/digitalcreativ/Pixelbild

---

## 17.11.2026 – Rastergrösse wählbar & Veröffentlichung auf GitHub

### Ausgangslage
- Das Pixelbild-Tool (`index.html`) war bereits vorhanden: festes Raster von 19 × 19 Feldern, 20 Malfarben, eigene Farbe, Radiergummi, «Alles löschen», Export als PNG (mit/ohne Rasterlinien), «Mitte anzeigen».
- Dazu ein Ordner `Beispielbilder` mit 8 Vorlagen (Bär, Daumen hoch, Herz, Kette, Puzzleteil, Regenbogen, Smiley, Stern).

### 1. Rastergrösse wählbar gemacht
**Wunsch:** Statt nur 19 × 19 auch 25 × 25 Pixel ermöglichen.

**Umsetzung (mit Claude Code):**
- Neue Auswahl **«Rastergrösse»** mit 15 × 15, 19 × 19, 25 × 25 und 31 × 31.
- **19 × 19 ist Standard** beim Öffnen der Seite.
- Nur ungerade Grössen, damit «Mitte anzeigen» weiterhin genau eine mittlere Zeile/Spalte hat.
- Beim Wechseln der Grösse wird das Raster neu aufgebaut; wurde schon gemalt, fragt das Tool vorher nach (das Bild wird sonst gelöscht).
- Die Felder passen sich automatisch an: höchstens 28 px gross, auf kleinen Bildschirmen (z.B. iPad, Handy) kleiner, damit das ganze Raster sichtbar bleibt.
- Der PNG-Export übernimmt die gewählte Rastergrösse.

### 2. Veröffentlichung auf GitHub
1. Repository **`Pixelbild`** auf github.com erstellt (öffentlich).
2. Repository mit **GitHub Desktop** auf den Computer geklont (Ordner `Vibe_Coding\Pixelbilder\Pixelbild`).
3. `index.html` und `Beispielbilder` in den geklonten Ordner kopiert.
4. In GitHub Desktop: **Commit to main** («Beispiele») und **Push origin** → Dateien sind auf GitHub.
5. **GitHub Pages** eingeschaltet: *Settings → Pages → Deploy from a branch → `main` / `(root)` → Save*.
6. Kontrolle: Die Webseite ist online und funktioniert.

### Gelernt / Stolpersteine
- **«/ (root)»** ist kein Ordner, sondern die zweite Auswahl neben `main` in den Pages-Einstellungen: Die Webseite kommt aus dem obersten Ordner des Repositorys.
- Nach dem Einschalten von GitHub Pages dauert es **1–2 Minuten**, bis die Seite erreichbar ist. Vorher erscheint «404». Notfalls mit **Strg + F5** neu laden.
- Es gibt nun **zwei Ordner**: den ursprünglichen im OneDrive (`Pixelbilder`) und den geklonten (`Pixelbilder\Pixelbild`). Nur Änderungen im geklonten Ordner gelangen über GitHub Desktop auf GitHub.
- Versehentlich entstand ein zweiter, leerer Klon unter `Leistungsnachweis\…\wahlfachgruppen2OS\Pixelbild`. Er wird nicht gebraucht und kann in GitHub Desktop entfernt werden.

### Ablauf für künftige Änderungen
1. Änderung an `Pixelbild\index.html` vornehmen (lassen).
2. GitHub Desktop: kurze Beschreibung eingeben → **Commit to main**.
3. **Push origin**.
4. Nach 1–2 Minuten ist die neue Version online.

### 3. Bild passt sich beim Ändern der Rastergrösse an
**Wunsch:** Wenn man z.B. auf 31 × 31 zeichnet und dann auf 19 × 19 wechselt, soll das Bild nicht gelöscht, sondern umgerechnet werden.

**Umsetzung:**
- Beim Wechseln der Rastergrösse wird das Bild auf die neue Grösse umgerechnet (verkleinert oder vergrössert). Die Nachfrage «Bild wird gelöscht» entfällt.
- So wird gerechnet: Jedes neue Feld schaut, welche alten Felder es überdeckt. Ist mindestens 30 % davon farbig, bekommt es die häufigste Farbe, sonst bleibt es weiss.
- Das Tool merkt sich das Originalbild: Wechselt man z.B. 31 → 19 → 31, ohne dazwischen zu malen, erscheint wieder genau das Originalbild. Sobald man im neuen Raster weitermalt, gilt das neue Bild als Original.
- Beim Verkleinern gehen feine Details verloren (z.B. dünne Linien werden manchmal unterbrochen oder etwas dicker).

### Ideen / offene Punkte
- …
