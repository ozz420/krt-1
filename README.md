# Keiretsu Forum Vietnam — Website

Institutional investor-relations website for **Keiretsu Forum Vietnam** (Chapter 54 of
Keiretsu Forum Global) and its **Keiretsu Crypto Fund** platform. Built as a
production React + TypeScript app from the Claude Design prototype.

**Vietnam Gateway for Global Capital** — bilingual (Vietnamese default · English),
four linked pages, restrained institutional motion.

## Stack

- **React 18** + **TypeScript** + **Vite**
- **react-router-dom** — real URLs with client-side routing
- Design-system tokens (colours, type, spacing) consumed as CSS custom properties
  from `src/styles/` — ported verbatim from the Keiretsu design system
- No UI framework: the brand primitives (Button, Input, Select, Checkbox, Icon)
  are hand-built to match the design-system components

## Getting started

```bash
npm install
npm run dev        # start the dev server (Vite)
npm run build      # typecheck + production build → dist/
npm run preview    # preview the production build
npm run typecheck  # type-check only
```

## Project structure

```
src/
  main.tsx               # entry — mounts <App/> inside <BrowserRouter>
  App.tsx                # routes: / · /about · /fund · /institutional
  content.ts             # bilingual (VI/EN) content dictionary — typed
  routes.ts              # nav order + path metadata
  context/AppContext.tsx # language state (persisted) + access-modal state
  components/
    ui/                  # Button · Input · Select · Checkbox · Icon · SectionHead
    layout/              # Header (sticky, responsive) · Footer · Layout
    AccessModal.tsx      # gated "Become a Member / Request Pack" modal
  pages/                 # Home · About · Fund · Institutional (+ CSS modules)
  styles/                # design-system tokens + global styles
public/
  images/                # photography & diagrams from the brand PDF
  *.svg                  # brand logos + pinwheel mark
```

## Features

- **Four pages** — Home (hero · 6-stat band · three value pillars · ink narrative),
  About (heritage ledger · Chapter 54 ink band · vision/mission · five sectors ·
  two-pillar model), Fund Platform (three-layer KCF·KRT·WE-BANK architecture ·
  US$50B allocation ledger · the 2026–2035 capital roadmap timeline · capabilities),
  and Institutional Investors (benefits · four-step engagement flow · request CTA).
- **VI ⇄ EN toggle** driving every string; language choice persists in `localStorage`
  and syncs `<html lang>`.
- **Gated access modal** with email validation, an accredited-investor gate, a
  success state, `Escape`-to-close and body-scroll lock. Footer newsletter capture too.
- **Fully responsive** — desktop-first at the 1320px institutional width, with
  tablet/mobile breakpoints (hamburger nav, stacked grids, fluid headline type).
- **Restrained motion** — sticky header blur past 24px scroll, subtle page fades,
  hover/press states. Honours `prefers-reduced-motion`.

## Notes / substitutions (from the design system)

- **Fonts** load from the Google Fonts CDN — **EB Garamond** (display),
  **Libre Franklin** (UI), **IBM Plex Mono** (data). These are the design
  system's noted substitutes for the brand's custom faces; swap when the
  official fonts are supplied.
- **Icons** are Lucide-style stand-ins for the brand's custom glyph set.
- Forms are front-end demos (no backend). Wire `AccessModal` and the footer
  newsletter to a real endpoint when available.

## Design source

The original Claude Design export is preserved for reference:

- `project/` — the HTML/CSS/JS prototype, design-system tokens, and assets
- `chats/` — the design conversation transcripts
