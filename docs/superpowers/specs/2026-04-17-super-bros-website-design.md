# Super Bro's Frankfurt — Website Design Spec
**Date:** 2026-04-17  
**Client:** Super Bro's GbR (Giuseppe Mazzella, Valentino Mazzella, Luca De Simone)  
**Type:** Multi-page static HTML, single-file per page  

---

## Research Summary

### People
- **Giuseppe & Valentino Mazzella** (the Bros) + cousin **Luca De Simone**
- Frankfurt-born Italians with roots in Naples and Calabria
- Great-grandfather from Naples married a Calabrian woman → family story

### Locations
**Nordend (Das Original, seit 2017)**
- Oeder Weg 55-57, 60318 Frankfurt am Main
- Tel: 069-26497580
- Email: ciao@super-bros.de
- Wolt: https://wolt.com/en/deu/frankfurt/restaurant/super-bros
- Hours: Mo closed, Di–Do 12:00–22:00, Fr 12:00–23:00, Sa 14:00–23:00, So 14:00–22:00

**Westend (Der Neue Bruder, seit 2024)**
- Grüneburgweg 78 / Parkstrasse 1, 60322 Frankfurt am Main
- Tel: 069-21029842
- Wolt: https://wolt.com/en/deu/frankfurt/restaurant/super-bros-westend

### Ratings
- Google: 4.5 ⭐ (3,473+ Bewertungen)
- Tripadvisor: 4.2/5 (160 reviews) — #7 of 84 Quick Bites Frankfurt

### Key Review Quotes
1. *"This is not just good pizza. It's the pizza. The kind that makes you close your eyes after the first bite, baked to absolute perfection."* — LaurMadrid, May 2025
2. *"Absolutely amazing. One of the best pizzas ever. Style: Vera napoletana. Champions League!!"* — Wolfgang W
3. *"100% Taste, 100% Italy. Fresh ingredients, thin base, crispy crust, baked in a wood-fired oven."* — Bazoo, Apr 2024

### Brand Assets (URLs)
- Logo wordmark PNG: `https://static.wixstatic.com/media/828df7_1501072510ba435897584519cfdfa708~mv2.png`
- Logo icon (pizza character): `https://static.wixstatic.com/media/828df7_4fda75d65ba84b2b827c4447ccedaa0e~mv2.png`
- Favicon: `https://static.wixstatic.com/media/f21c7c_31155db5f1fe45c4bc3a117aace2ad2d~mv2.png`
- OG hero image: `https://static.wixstatic.com/media/f21c7c_4632dd6af43d4229a34b1f919e9bf1b5~mv2.png/v1/fill/w_2500,h_1875,al_c/f21c7c_4632dd6af43d4229a34b1f919e9bf1b5~mv2.png`
- Story hero (pizza close-up): `https://static.wixstatic.com/media/f21c7c_0e4c1df8373d47d8904e5e50d1911a88~mv2.png/v1/crop/x_341,y_405,w_1670,h_1524/fill/w_538,h_491,al_c,q_85,usm_0.66_1.00_0.01,enc_avif,quality_auto/Super%20Bro's%20Hero.png`
- Tripadvisor photo: `https://media-cdn.tripadvisor.com/media/photo-w/19/6a/bb/cb/super-bro-s.jpg`

### Official Story Text (from super-bros.de/story — use verbatim on story.html)
> Unser Urgroßopa, ursprünglich Neapolitaner, heiratete eine Kalabresin. Aus dieser Vereinigung entsprangen nicht nur viele Bambini, sondern auch etliche kulinarische Leckerbissen… Geboren und aufgewachsen in Frankfurt am Main, verbrachten wir unsere Ferien immer bei unserer Familie im sonnigen Kalabrien. Dort diente das Essen nicht nur dem Zweck, satt zu werden. Es war vielmehr ein gesellschaftliches Ereignis, das mit Freunden und Nachbarn zelebriert wurde. Während unsere Eltern die Hauptspeise zubereiteten, meistens Pasta mit selbstgemachter Tomatensauce, zauberte unser Papanonno seine berühmt berüchtigte Pizza mit ausgewählten und frischen Zutaten. Dieses Stück Heimat haben wir uns auch in Deutschland bewahrt, und bringen unsere Tradition und das damit verbundene Lebensgefühl in das schöne Frankfurt. Wir sind Zuhause im Nordend (since 2017) sowie im Westend (since 2024). Orte der Geselligkeit und des Genießens. Schön, dass Du da bist!

---

## Design System

### Color Palette
```
--rosa:       #E8547A   (primary brand — warm hot pink, from pizza box)
--rosa-light: #F2A0B4   (soft hover / accent)
--rosa-dark:  #C43860   (CTA hover state)
--cream:      #FDF8F2   (background — warm not cold)
--cream-2:    #F5EDE2   (section alternation)
--charcoal:   #1A1614   (text — near black, warm)
--charcoal-2: #3D3330   (secondary text)
--mid:        #8C7B74   (muted text)
--white:      #FFFFFF
```

### Typography
- **Display (Hero, Section Titles):** `Archivo Black` — fat, geometric, modern, zero nostalgia  
  → `font-weight: 900`, `letter-spacing: -0.03em`, uppercase for hero
- **Subheads / Labels:** `Archivo` (regular/medium) — same family, less weight
- **Body:** `Inter` — clean legibility, pairs perfectly with Archivo
- **Accent / Italian phrases:** `Playfair Display` Italic — sparingly, for atmosphere (chapter titles, pullquotes)

Google Fonts import:
```
Archivo+Black:wght@400&Archivo:wght@400;500;600&Inter:wght@300;400;500&Playfair+Display:ital,wght@1,400;1,700
```

### Motion Stack
- Lenis for smooth scroll (every page)
- Motion.js for all scroll-triggered animations
- IntersectionObserver for section reveals
- CSS transitions for hover states (300ms ease)

---

## Page Architecture

### Shared Components (same across all 4 pages)

**Navigation**
- Fixed, transparent on load → white/cream on scroll (backdrop-filter blur)
- Mobile: hamburger → full-screen overlay
- Left: Logo wordmark (SVG from Wix CDN)
- Center links (desktop): Home · Nordend · Westend · Story
- Right: Instagram icon + Facebook icon + "Bestellen bei Wolt" button (rosa, pill shape)

**Footer**
- Dark background (charcoal)
- Two columns: Nordend address + Westend address
- Social icons (Instagram, Facebook)
- Wolt links for both locations
- © Super Bro's GbR · Impressum · Datenschutz
- Small tagline: *"La Passione per la Pizza. Seit 2017 im Herzen von Frankfurt."*

---

### Page 1: index.html (Startseite)

**Section 1: Hero**
- Full viewport height
- Background: big, bold typography as texture — "PIZZA" in massive rosa letters behind content, opacity 0.06
- Rosa gradient from bottom
- Center: Logo icon (pizza mascot character) + claim
- Claim: **"Neapel. Kalabrien. Frankfurt."**
- Subline: *"Neapolitanische Pizza — ehrlich, lebendig, fatto con amore."*
- CTA: "Jetzt bestellen" → Wolt / "Speisekarte" → menu link
- Scroll indicator (arrow animation)
- Intro animation: logo fades + slides up on load

**Section 2: La Storia (Story Teaser)**
- Two columns on desktop, stacked on mobile
- Left: Chapter-title in Playfair italic "Wie ein Teig eine Familie zusammenhält." + 3–4 lines of the story + "Lies unsere Geschichte →" link to story.html
- Right: Pizza close-up photo (story hero from Wix CDN)
- Background: cream-2

**Section 3: Unsere Standorte**
- Two cards side by side (stack on mobile)
- Card 1 — Nordend: since 2017, Oeder Weg, hours, Wolt CTA, "Das Original"
- Card 2 — Westend: since 2024, Grüneburgweg, "Der Neue Bruder", Wolt CTA
- Cards in rosa background with cream text OR dark background
- Hover: subtle lift + shadow

**Section 4: Das Urteil der Gäste (Reviews)**
- Google rating: ★★★★½ 4.5 — displayed large and proud
- 3 review cards (cards slide in on scroll)
- Quote 1, Quote 2, Quote 3 from research above

**Section 5: Instagram Grid**
- Section title: "Folg uns, aber besser: komm vorbei."
- 6 Instagram embed images (use direct Instagram oEmbed or hardcoded @superbrosfrankfurt posts)
- Alternatively: Instagram grid as decorative element with link to @superbrosfrankfurt
- CTA: "@superbrosfrankfurt auf Instagram" → link

**Section 6: Bestellen / CTA**
- Full-width rosa background
- Large text: "Hunger? Bestell dir die beste Pizza Frankfurts nach Hause."
- Wolt logos/links for both locations

---

### Page 2: nordend.html

**Hero**
- Dark background (charcoal), rosa accent elements
- "Nordend — Das Original" as large display type
- Subline: "Seit 2017 im Oeder Weg. Hier hat alles angefangen."
- Address + phone + hours prominently shown

**Section: Die Geschichte beginnt hier**
- Short text about Nordend being the OG location, 2017, the stone oven, the neighborhood
- 1-2 food photos from Tripadvisor CDN

**Section: Öffnungszeiten**
- Clean grid: Mo Ruhetag, Di–Do 12–22, Fr 12–23, Sa 14–23, So 14–22

**Section: Speisekarte**
- "Was auf den Tisch kommt" — 4-6 iconic neapolitan pizza types (Margherita, Diavola, Bufala, etc.) as showcase cards
- "Gesamte Speisekarte" → https://www.super-bros.de/menu

**Section: Anfahrt**
- Embedded Google Maps (Oeder Weg 55-57)
- Address card with CTA phone + Wolt link

---

### Page 3: westend.html

**Hero**
- Rosa background, charcoal text (inverted from Nordend)
- "Westend — Der neue Bruder" 
- Subline: "Seit 2024 am Grüneburgweg. Gewachsen aus Liebe zur Pizza."

**Section: Der Neue Bruder**
- Text: The Westend is the younger sibling — same DNA, new energy. The Grüneburgweg neighborhood deserves great pizza.
- Slightly different energy: maybe more cocktail/aperitivo culture? If at Westend they do salads/desserts (scraped from Wix), show that.

**Section: Öffnungszeiten** (to be filled with real Westend hours — show as TBD or same as Nordend until confirmed)

**Section: Anfahrt**
- Embedded Google Maps (Grüneburgweg 78)
- Address + Wolt link

---

### Page 4: story.html

**Structure:** Cinematic scrolling journey. 3 chapters with generous spacing.

**Opening Screen**
- Full-screen: dark background, white Playfair italic title
- *"La Passione per la Pizza"*
- Scroll prompt to begin

**Chapter 1: Neapel**
- Large italic chapter label: "I. Neapel"
- Text block (part of story about Urgroßopa)
- Visual: old-world texture / map of Italy silhouette (CSS drawn)

**Chapter 2: Kalabrien**
- "II. Kalabrien"
- Text block (the summers, the pizza of Papanonno, the family meals)
- Visual: pizza photo, sun motif

**Chapter 3: Frankfurt**
- "III. Frankfurt"
- Text block (bringing it home, since 2017)
- CTA: "Komm uns besuchen → Nordend / Westend"

**Full Story Block**
- The complete official story text as a beautifully typeset paragraph

---

## Technical Spec

- Single-file HTML per page (CSS + JS embedded)
- Mobile-first, 360–390px → 1440px
- Libraries via CDN: Lenis, Motion.js
- All images: loading="lazy", alt text required
- Google Fonts: preconnect + href
- OG tags + meta description on every page
- Favicon from Wix CDN
- Google Maps embed: iframe with `loading="lazy"`

## Animations

**Every page:**
- Lenis smooth scroll: `new Lenis({ autoRaf: true })`
- Nav: fade + slide down on load
- Hero: staggered text reveal (lines animate up one by one)
- Sections: fade + translateY(30px) → 0 on IntersectionObserver

**story.html specifically:**
- Chapter labels animate in as scroll reaches each section
- Parallax on chapter background images
- Pull-quotes scale up slightly on scroll

## File Structure
```
clients/super-bros/
  index.html
  nordend.html
  westend.html
  story.html
```

## Deployment
- GitHub Pages: https://sempergo.github.io/semp-studios2/clients/super-bros/
- Commit after each page completion
