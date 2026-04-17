# Super Bro's Website Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Build a 4-page multi-site for Super Bro's Frankfurt (index, nordend, westend, story) — rosa brand, Archivo Black display, cinematic story page.

**Architecture:** Single-file HTML per page with embedded CSS+JS. Mobile-first (360px → 1440px). Shared design system via CSS custom properties repeated per file.

**Tech Stack:** Vanilla HTML/CSS/JS, Lenis (smooth scroll), Motion.js (animations), Google Fonts (Archivo Black + Inter + Playfair Display), GitHub Pages deployment.

---

### Task 1: index.html — Startseite

**Files:**
- Create: `clients/super-bros/index.html`

- [ ] Create `clients/super-bros/index.html` with full page: nav, hero, story teaser, locations, reviews, footer
- [ ] Commit + push
- [ ] Wait for GitHub Pages deploy (~60s), then Firecrawl screenshot at https://sempergo.github.io/semp-studios2/clients/super-bros/
- [ ] Fix any visual issues found in screenshot

### Task 2: story.html — Cinematic Story

**Files:**
- Create: `clients/super-bros/story.html`

- [ ] Create `clients/super-bros/story.html` with cinematic 3-chapter scroll experience
- [ ] Commit + push + Firecrawl screenshot review

### Task 3: nordend.html — Location Page

**Files:**
- Create: `clients/super-bros/nordend.html`

- [ ] Create nordend.html with location info, hours, map embed, menu CTA
- [ ] Commit + push + Firecrawl screenshot review

### Task 4: westend.html — Location Page

**Files:**
- Create: `clients/super-bros/westend.html`

- [ ] Create westend.html (rosa hero, different energy from nordend)
- [ ] Commit + push + Firecrawl screenshot review + output live URL
