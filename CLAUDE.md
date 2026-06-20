# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Informational website for **Tatiana Isaza**, a psychologist. The goal is to present her services and allow patients to contact her or schedule appointments. The site is a single-page layout with anchor-based navigation.

**Stack:** Astro 5 + Tailwind CSS v4 + Netlify Forms + Netlify Hosting

## Commands

```bash
# Install dependencies
npm install

# Start dev server (localhost:4321)
npm run dev

# Build for production
npm run build

# Preview production build locally
npm run preview
```

## Architecture

Single `src/pages/index.astro` assembles all sections in order. Each section is an isolated component under `src/components/`. The base HTML shell (head, meta, fonts) lives in `src/layouts/Layout.astro`.

**Data layer:** `src/data/servicios.js` holds the services list as a plain JS array — edit this file to add, remove, or rename services without touching component markup.

**Contact form:** Uses Netlify Forms (`netlify` attribute on the `<form>` tag). No backend or third-party account needed beyond Netlify hosting. Form submissions arrive at Tatiana's email automatically.

**WhatsApp button:** `src/components/BotonWhatsApp.astro` renders a fixed floating button visible on all scroll positions. The phone number is set directly in that component.

## Design Tokens

This project uses **Tailwind v4**, which has no `tailwind.config.mjs`. Colors and typography are defined via `@theme` blocks inside `src/styles/global.css`. The palette is soft and warm: sage green, warm white, dusty rose accent. Change values there to update the entire site consistently.

## Deployment

The site deploys automatically to Netlify on every push to `main`. No manual build step needed. Netlify Forms activates automatically after the first production deploy — it does **not** work in `npm run dev` (forms are processed by Netlify's CDN, not the local dev server).

## Content Placeholders

All text and images are placeholders until Tatiana provides real content. Images live in `public/images/`. Replacing a placeholder is a straight file swap — filenames are referenced directly in the components.
