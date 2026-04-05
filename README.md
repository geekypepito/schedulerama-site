# ScheduleRama — Astro Site

Converted from the v8 static HTML site. Built with [Astro](https://astro.build) — zero JS by default, fast static output.

## Project Structure

```
schedulerama-astro/
├── public/
│   └── images/
│       └── logo.png          # ScheduleRama shield logo
├── src/
│   ├── layouts/
│   │   └── Base.astro        # Root layout: <html>, nav, footer, SEO
│   ├── components/
│   │   ├── Nav.astro         # Navigation with dropdowns
│   │   └── Footer.astro      # Site footer
│   ├── styles/
│   │   └── global.css        # Design tokens, resets, shared components
│   └── pages/
│       ├── index.astro       # Homepage
│       ├── about.astro
│       ├── pricing.astro
│       ├── contact.astro
│       ├── product/
│       │   ├── schedule-management.astro
│       │   ├── group-scheduler.astro
│       │   ├── game-finder.astro
│       │   ├── requests-inbox.astro
│       │   ├── realtime-messaging.astro
│       │   ├── facility-operations.astro
│       │   ├── operational-workflows.astro
│       │   ├── organization-data.astro
│       │   └── reports-import.astro
│       ├── solutions/
│       │   ├── athletic-directors.astro
│       │   ├── transportation.astro
│       │   ├── maintenance.astro
│       │   ├── game-officials.astro
│       │   ├── coaches.astro
│       │   ├── league-admins.astro
│       │   └── super-admins.astro
│       └── resources/
│           ├── user-guide.astro
│           ├── feature-matrix.astro
│           ├── release-notes.astro
│           └── faq.astro
├── astro.config.mjs
└── package.json
```

## Getting Started

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # Output to dist/
npm run preview  # Preview the built site
```

## Design System

All design tokens live in `src/styles/global.css`:

```css
--bg: #f2f0eb        /* Warm off-white background */
--bg-warm: #e8e4dc   /* Slightly darker warm bg */
--navy: #1b2d4f      /* Primary navy */
--navy-deep: #0f1c30 /* Deep navy (nav, hero bg) */
--orange: #e85f17    /* Primary brand orange */
--teal: #1aab8a      /* Confirmation / success */
```

**Fonts:** Barlow Condensed (headings), Barlow (body), JetBrains Mono (labels/tags)

## Deploying

### Netlify
Push to GitHub, connect repo in Netlify. Build command: `npm run build`. Publish directory: `dist`.

### Vercel
```bash
npm i -g vercel
vercel
```

### Cloudflare Pages
Build command: `npm run build`. Output directory: `dist`.

## Updating the Site URL

Change `site` in `astro.config.mjs`:
```js
export default defineConfig({
  site: 'https://schedulerama.com',
});
```

## Notes

- Page-specific CSS lives in `<style>` blocks inside each `.astro` file
- The Nav component accepts an `activeSection` prop (`'product' | 'solutions' | 'resources' | 'company'`) to highlight the current section
- Scroll-triggered `.fade-up` animations are initialized in `Base.astro`
- All internal links use absolute paths (e.g. `/product/game-finder/`)
