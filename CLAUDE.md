# Globale Anweisungen

## Ziel

Der Kunde soll die Website sehen und geflasht sein. Er soll das Gefühl haben: **"Das ist meins."** So gut, so persönlich, so genau auf ihn zugeschnitten — dass er gar nicht mehr nein sagen kann.

Qualitätsmaßstab: Nicht "gut genug". Nicht "solide". Sondern: würde dieser Kunde das stolz seinen Freunden zeigen?

**Fokus: Gastronomie.** Alle Websites in diesem Projekt sind für Restaurants, Cafés, Bars und ähnliche Gastronomiebetriebe.

## Arbeitsweise

Autonom arbeiten. Nicht nachfragen, nicht zögern. Research → Bauen → Review → Deployen. Am Ende Live-URL ausgeben.

---

## Workflow für neue Kunden-Website

**Schritt 1 — Research**
- Alte Website mit Firecrawl scrapen → nur Inhalte extrahieren: Leistungen, Adresse, Öffnungszeiten, Menü, Team
- Alte Website mit Playwright aufrufen und Screenshot machen → echte Fotos (Gerichte, Räume, Produkte, Team) identifizieren und URLs notieren
- Google Maps → Adresse, Öffnungszeiten, Bewertungen, Sterne
- Instagram/Social Media mit Playwright → echte Fotos, Stimmung, Zielgruppe
- Logo identifizieren und URL notieren
- NIEMALS Design, Farben, Fonts oder Layout von der alten Website übernehmen — diese sind oft schlecht
- Texte immer komplett neu schreiben: emotional, überzeugend, auf die Zielgruppe zugeschnitten

**Schritt 2 — Design System (komplett neu)**
- UI/UX Pro Max Skill für Stil-Empfehlung passend zu Branche + Zielgruppe
- Eigene Farbpalette — professionell, modern, emotional passend zur Gastronomie
- Google Fonts — frisch auswählen, passend zum Stil
- Echte Fotos vom Unternehmen verwenden (aus Schritt 1)
- Unsplash nur wenn keine ausreichend guten echten Fotos vorhanden

**Schritt 3 — Bauen**
- Single-File HTML mit eingebettetem CSS + JS
- Mobile-first — Mobile ist die Hauptplattform, Desktop muss genauso gut sein
- Hohe visuelle Qualität: klare Hierarchie, Whitespace, professionelle Typografie
- Echte Inhalte — keine Platzhalter wie "Lorem ipsum"
- **21st.dev MCP** für fertige UI-Komponenten nutzen:
  - `mcp__magic__21st_magic_component_builder` → Hero, Cards, Nav, Sections generieren
  - `mcp__magic__21st_magic_component_refiner` → Komponenten verfeinern und anpassen
  - `mcp__magic__21st_magic_component_inspiration` → Design-Inspiration holen
  - `mcp__magic__logo_search` → Kunden-Logo oder Branchen-Logos suchen

**Schritt 4 — Review** (Checkliste — alle Punkte müssen erfüllt sein)
- [ ] Mobile sieht perfekt aus (375px) — das ist die Priorität
- [ ] Desktop sieht genauso gut aus (1440px)
- [ ] Jede Section hat einen klaren CTA
- [ ] Alle Animationen und Scroll-Effekte laufen flüssig
- [ ] Keine Platzhalter-Texte, keine leeren Felder
- [ ] Fotos sind scharf, appetitlich und emotional
- [ ] Ladezeit fühlt sich schnell an
- [ ] OG-Tags, Meta-Description, Favicon vorhanden
- [ ] Lazy Loading auf allen Bildern
- [ ] Würde der Kunde das stolz seinen Freunden zeigen?

**Schritt 5 — Deployen**
- Committen und pushen
- GitHub Pages aktivieren falls noch nicht aktiv:
  ```bash
  gh api repos/{owner}/{repo}/pages --method POST --field source='{"branch":"main","path":"/"}' 2>/dev/null || true
  ```
- Live-URL ausgeben: `https://sempergo.github.io/semp-studios2/clients/{kundenname}/`

---

## Animationen & Scroll

Jede Website bekommt beide Libraries via CDN (direkt vor `</head>`):

```html
<!-- Smooth Scroll -->
<script src="https://unpkg.com/lenis@latest/dist/lenis.min.js"></script>
<!-- Animationen -->
<script src="https://cdn.jsdelivr.net/npm/motion@latest/dist/motion.js"></script>
```

Lenis initialisieren:
```js
const lenis = new Lenis({ autoRaf: true });
```

Standard-Elemente die jede Gastronomie-Website bekommt:
- **Intro-Animation** — Logo oder Claim blendet beim Laden ein
- **Parallax** — Hero-Bild oder Hintergründe scrollen langsamer als Content
- **Scroll-Animationen** — Sections und Elemente fahren beim Einblenden rein (Motion.animate + IntersectionObserver)
- **Micro-Interactions** — Buttons und Links reagieren spürbar auf Hover/Click

---

## Copywriting-Framework

Jede Section folgt einer klaren Struktur. Darüber hinaus gibt es Freiheit für brandeigene Abschnitte die zur Persönlichkeit des Restaurants passen.

**Hero**
- Emotionaler Claim (1 Zeile, trifft das Gefühl des Restaurants)
- Subline (was, wo, für wen)
- CTA: "Jetzt Tisch reservieren" oder "Speisekarte entdecken"

**Über uns**
- Geschichte des Restaurants (wann, wie, warum)
- Leidenschaft und Werte
- Einladung an den Gast

**Speisekarte / Highlights**
- Nicht die komplette Karte — 3–6 Highlight-Gerichte
- Jedes Gericht mit appetitlicher, emotionaler Beschreibung (nicht nur Zutaten)
- Foto wenn vorhanden

**Bewertungen**
- Google-Sterne-Bewertung prominent
- 2–3 echte Zitate aus Google Maps

**Kontakt & Reservierung**
- Adresse, Öffnungszeiten, Telefon, E-Mail
- Google Maps eingebettet
- CTA wiederholen: "Tisch reservieren"

**Brandeigene Abschnitte** (Beispiele je nach Konzept)
- Weinauswahl, Cocktailkarte, Eventbereich, Chefkoch-Vorstellung, Lieferservice, etc.

---

## Technische Pflicht-Elemente

Jede Website bekommt ohne Ausnahme:

```html
<!-- Meta -->
<meta name="description" content="...">

<!-- OG-Tags -->
<meta property="og:title" content="...">
<meta property="og:description" content="...">
<meta property="og:image" content="...">
<meta property="og:url" content="...">

<!-- Favicon -->
<link rel="icon" href="favicon.ico">
```

- Alle `<img>` Tags bekommen `loading="lazy"`
- Kein Bild ohne `alt`-Text

---

## Git-Workflow
- Nach jeder bedeutsamen Änderung committen und zu GitHub pushen
- Conventional Commits verwenden (feat, fix, refactor, docs, chore)

---

## HTML-Projekte (Single-File)

- Kein Framework, kein Build-System, kein npm
- Alles in einer einzigen `.html`-Datei (CSS + JS eingebettet)
- Lenis + Motion via CDN sind Pflicht
- Nach jeder Änderung: committen und pushen

---

## Ordnerstruktur & URLs

Jeder Kunde bekommt einen eigenen Ordner:
```
clients/<kundenname>/index.html
```

Live-URL bei GitHub Pages:
```
https://sempergo.github.io/semp-studios2/clients/<kundenname>/
```
