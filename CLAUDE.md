# Rebecca L. Norrington — Website Project

## Overview

Client website redesign. Astro 5 demo deployed to Vercel for client approval before WordPress migration.

- **Live demo:** https://rebecca-norrington-demo.vercel.app
- **GitHub:** https://github.com/Bikashsb/rebecca-norrington-website
- **WordPress (current site):** https://rebeccanorrington.com
- **Client email:** rln@rebeccanorrington.com

## Tech Stack

- **Astro 5** — static site generator
- **Tailwind CSS v4** — uses `@import "tailwindcss"` + `@theme {}` in `src/styles/global.css` (no `tailwind.config.js`)
- **Alpine.js** — mobile nav, accordions, carousel interactivity

## Design System

### Colors (Tailwind tokens)
```
cream:        #FAF7F2   (page background)
cream-dark:   slightly darker cream (card backgrounds)
terracotta:   #C4774A   (primary accent)
sage:         #8BA888   (secondary accent)
charcoal:     #2C2C2C   (body text)
charcoal-light: lighter charcoal (secondary text)
gold:         #D4A853   (eyebrow text, highlights)
```

### Fonts
- `font-display` → Cormorant Garamond (headings)
- Body → Poppins (loaded via Google Fonts in `BaseLayout.astro`)

## Workflow

After every change: `git add` → `git commit` → `git push` → Vercel auto-deploys.
Never need to run `vercel deploy` manually.

## Page Structure

15 pages in `src/pages/`:
`index`, `about`, `books`, `services`, `retreats`, `testimonials`, `ask-rebecca`, `interviews`, `donation`, `consultation`, `media`, `contact`, `privacy`, `terms`, `blog/index`, `blog/[slug]`

## Hero Section Pattern

All inner pages use this standard cinematic hero:

```astro
<section class="relative min-h-[60vh] flex items-center overflow-hidden">
  <div class="absolute inset-0">
    <img src="/images/IMAGE.jpg" alt="" class="w-full h-full object-cover object-center" />
    <div class="absolute inset-0 bg-gradient-to-br from-charcoal/90 via-charcoal/60 to-charcoal/20"></div>
  </div>
  <div class="relative z-10 max-w-7xl mx-auto px-6 pt-28 md:pt-36 pb-16 w-full">
    <p class="text-gold text-sm tracking-[0.2em] uppercase mb-4 font-medium">Eyebrow</p>
    <h1 class="font-display text-5xl md:text-6xl lg:text-7xl font-light text-white leading-tight tracking-tight">Title</h1>
    <p class="mt-5 text-white/85 text-lg max-w-lg">Subtitle</p>
  </div>
</section>
```

Key rules:
- Always `object-cover object-center` on hero images (never `object-top`)
- Nav is `fixed top-0 z-50` ~72-80px tall → content div always needs `pt-28 md:pt-36`
- Gradient: `from-charcoal/90 via-charcoal/60 to-charcoal/20`
- Homepage hero uses `min-h-screen` (taller); inner pages use `min-h-[60vh]` or `min-h-[65vh]`

### Hero Image Assignments

| Page | Image |
|------|-------|
| `index.astro` | `askrebecca2.jpg` |
| `about.astro` | `howcanihelp.jpg` |
| `services.astro` | `rebecca-interview.jpg` |
| `books.astro` | `slide2-1-1024x683-700x467.jpg` |
| `testimonials.astro` | `slide2-1-1024x683-700x467.jpg` |
| `contact.astro` | `contact-rebecca.jpeg` |
| `ask-rebecca.astro` | `askrebecca2.jpg` |
| `interviews.astro` | `podcast-rebecca.jpg` |
| `retreats.astro` | `retreat-rebecca.jpeg` |

## Key External Links

| Purpose | URL |
|---|---|
| Calendly (consultation) | https://calendly.com/realityspirituality |
| Donation | https://www.paypal.com/paypalme/rebeccalnorrington/ |
| One-on-One $85 | https://www.paypal.com/paypalme/rebeccalnorrington/85 |
| Truth About Happiness $240 | https://www.paypal.com/paypalme/rebeccalnorrington/240 |
| Fitness classes $195 | https://www.paypal.com/paypalme/rebeccalnorrington/195 |
| Books (Amazon) | https://amzn.to/3PQttPP |
| YouTube | https://www.youtube.com/@RebeccaNorrington |
| Radio | http://www.realityspirituality.com/ |
| Facebook | https://www.facebook.com/RealitySpirituality |
| Instagram | https://www.instagram.com/realityspirituality/ |
| LinkedIn | https://www.linkedin.com/in/rebecca-l-norrington-b0849015/ |
| Twitter | https://twitter.com/rlnorrington |

## Book

- **Title:** Programmed for Unhappiness: Exposing the Untold Truth
- **Series:** RealitySpirituality
- **ASIN:** B0D3YV7913 (Kindle) / B0D3HVWXJC / B0D3MGSKCK (print)
- **Released:** September 26, 2024 — International Bestseller
- **Cover:** `/public/images/book-cover.jpg`

## Data Files

- `src/data/services.json` — services + pricing + PayPal URLs
- `src/data/testimonials.json` — client testimonials
- `src/data/qa.json` — Ask Rebecca Q&A (11 items)
- `src/data/books.json` — book info

## Important Notes

- Images must live in `/public/images/` (not `src/assets/`) for Astro static serving
- Favicon: Rebecca's purple heart logo (`/public/favicon-32.png`, `favicon-192.png`, `favicon-180.png`) — set in `BaseLayout.astro`
- Her philosophy/brand: **RealitySpirituality**
- Site icon source: `https://rebeccanorrington.com/wp-content/uploads/2020/09/cropped-rebecca_heart_-removebg-preview-192x192.png`

## Status

- [x] All 15 pages built
- [x] Deployed to Vercel
- [x] Book cover wired up
- [x] PayPal links per service
- [x] Favicon (purple heart) set
- [ ] Client approval of Vercel demo
- [ ] WordPress migration after approval
