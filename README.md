# Vishnu Kumar — Portfolio

> *A cinematic, single-file developer portfolio built without frameworks, bundlers, or build steps.*

[![HTML](https://img.shields.io/badge/HTML5-Single%20File-c9a84c?style=flat-square&logo=html5&logoColor=black)](./vishnu_portfolio.html)
[![CSS](https://img.shields.io/badge/CSS3-Vanilla-c9a84c?style=flat-square&logo=css3&logoColor=black)](./vishnu_portfolio.html)
[![JS](https://img.shields.io/badge/JavaScript-Vanilla%20ES6%2B-c9a84c?style=flat-square&logo=javascript&logoColor=black)](./vishnu_portfolio.html)
[![No Dependencies](https://img.shields.io/badge/Dependencies-Zero-c9a84c?style=flat-square)](./vishnu_portfolio.html)
[![Deploy: Vercel](https://img.shields.io/badge/Deploy-Vercel%20Ready-c9a84c?style=flat-square&logo=vercel&logoColor=black)](https://vercel.com)

---

## Overview

This is the personal portfolio of **Vishnu Kumar**, Senior Software Engineer at Paytm Money. The portfolio is a single `vishnu_portfolio.html` file — no Node.js, no npm, no build pipeline. Drop it anywhere and it works.

Designed around the **"Engineering Noir"** aesthetic: deep charcoal blacks, warm amber-gold accents, editorial Playfair Display typography, and a particle canvas background. Built to make a hiring manager at a MAANG company stop scrolling.

---

## Live Preview

```
open vishnu_portfolio.html
```

Or deploy to Vercel in 30 seconds — see [Deployment](#deployment) below.

---

## Sections

The portfolio is structured as **9 sections**, each mapped to a unique `id` anchor:

| # | Section | ID | Description |
|---|---|---|---|
| — | Hero | `#hero` | Name, tagline, animated stat counters, CTA buttons |
| 01 | About | `#about` | Bio, tech pills, portrait |
| 02 | Experience | `#experience` | Tabbed work history — 3 roles at Paytm |
| 03 | Origins | `#college` | College internships timeline + snapshot panel |
| 04 | Projects | `#projects` | 9-project bento grid with featured cards |
| 05 | Skills | `#skills` | Skill groups + technology word cloud |
| 06 | Awards | `#achievements` | 6 achievement cards |
| 07 | Beyond Code | `#beyond` | Podcast, GitHub Constellation, community |
| 08 | Contact | `#contact` | Links, contact info, target role |

---

## Features

### Visual & Animation
- **Custom magnetic cursor** — amber dot + lagged ring that scales on hover, powered by `requestAnimationFrame` lerp
- **Particle canvas background** — 80 ambient gold particles with proximity-based connection lines, fixed behind all content
- **Scroll reveal** — all content sections use `IntersectionObserver` with `threshold: 0.05` to fade-slide into view
- **Hero stat counters** — ease-out cubic count-up animation triggered on scroll (6M, 95M, 99.9%, 1920)
- **Staggered hero entrance** — name, role, description, buttons, and stats each animate in with CSS `animation-delay`
- **Sticky nav transition** — padding shrinks and frosted-glass background appears after 60px scroll

### Navigation & Interaction
- **Experience tabs** — click to switch between 3 job panels with a smooth fade transition
- **Smooth scroll** — all anchor links use `scrollIntoView({ behavior: 'smooth' })`
- **Nav CTA** — "Hire Me" button links directly to `mailto:`
- **Project links** — GitHub and live links on relevant project cards

### Typography
- `Playfair Display` — display serif for all headings, hero name, section titles. Creates editorial drama
- `JetBrains Mono` — monospace for labels, section tags, chips, nav links, badges
- `DM Sans` — clean sans-serif for all body text and descriptions

### Design System
All colours are defined as CSS custom properties in `:root`:

```css
--black:    #0a0a0a   /* page background */
--deep:     #111      /* deeper bg for variety */
--card:     #161616   /* card/panel backgrounds */
--border:   #1e1e1e   /* default border colour */
--border2:  #2a2a2a   /* secondary border on hover */
--gold:     #c9a84c   /* primary accent — all highlights */
--gold-dim: rgba(201,168,76,.1)   /* subtle gold tint fills */
--gold-glow:rgba(201,168,76,.25)  /* glow shadow on hover */
--white:    #f0ede8   /* warm off-white text */
--muted:    #6b6b6b   /* secondary text */
--muted2:   #3a3a3a   /* tertiary / placeholder text */
```

---

## File Structure

```
portfolio/
├── vishnu_portfolio.html    ← Everything. The entire portfolio.
└── README.md                ← This file
```

That's it. One file. No `node_modules`. No `package.json`. No `webpack.config.js`.

---

## Deployment

### Vercel (recommended — 30 seconds)

```bash
# Install Vercel CLI once
npm i -g vercel

# Deploy from the folder containing the HTML file
vercel

# Follow prompts — select the folder, accept defaults
# Your site will be live at https://your-project.vercel.app
```

For a custom domain, go to your Vercel project → Settings → Domains → Add `vishnu.dev` (or your domain).

### Netlify

Drag and drop `vishnu_portfolio.html` onto [netlify.com/drop](https://app.netlify.com/drop). Live in seconds.

### GitHub Pages

```bash
git init
git add vishnu_portfolio.html README.md
git commit -m "Initial portfolio"
git branch -M main
git remote add origin https://github.com/vish1811/portfolio.git
git push -u origin main
```

Then go to repo → Settings → Pages → Source: `main` branch → `/root`.

Your portfolio will be live at `https://vish1811.github.io/portfolio/vishnu_portfolio.html`.

> **Tip:** Rename `vishnu_portfolio.html` to `index.html` for a cleaner root URL — `https://vish1811.github.io/portfolio/`.

### Local

```bash
# No server needed — just open the file
open vishnu_portfolio.html          # macOS
start vishnu_portfolio.html         # Windows
xdg-open vishnu_portfolio.html      # Linux
```

---

## Customisation Guide

Since everything lives in one file, all edits are in `vishnu_portfolio.html`.

### Updating Personal Info

| What to change | Where to find it |
|---|---|
| Name / headline | `#hero` section — `.hero-h1` and `.hero-role` |
| Hero description | `.hero-desc` paragraph |
| Hero stat numbers | `data-target` attributes on `.stat-val` elements |
| About paragraphs | `.about-body` in `#about` section |
| Tech pills in about | `.tech-pills` div |
| Email address | 4 places — nav CTA, `#contact` link list, info panel, footer |
| LinkedIn / GitHub URLs | `#contact` `.ct-link-list` and footer |

### Adding a New Job

1. Add a new `.exp-tab` in the tabs sidebar:
```html
<div class="exp-tab" data-panel="ep3">
  <div class="etab-date">Jan 2025 – Present</div>
  <div class="etab-co">Company Name</div>
  <div class="etab-role">Role · Location</div>
</div>
```

2. Add a matching `.exp-panel` in the panels area:
```html
<div class="exp-panel" id="ep3">
  <div class="panel-head">
    <div class="panel-title">Role <span>@ Company</span></div>
    <div class="panel-badge">Jan 2025 – Present · Location</div>
    <div class="chip-row">
      <span class="chip">Java</span>
    </div>
  </div>
  <ul class="ach-list">
    <li class="ach-item">
      <div class="ach-num">01</div>
      <div class="ach-body">
        <strong>Achievement Title</strong>
        <p>Description of what you built and its impact.</p>
      </div>
    </li>
  </ul>
</div>
```

### Adding a New Project

Add a `.proj-card` inside `.projects-grid`. Use `class="proj-card featured"` to span 2 columns:

```html
<div class="proj-card">
  <div class="proj-num">/ 10</div>
  <div class="proj-name">Project Name</div>
  <p class="proj-desc">What it does and why it matters.</p>
  <div class="proj-techs">
    <span class="proj-t">Java</span> · <span class="proj-t">Redis</span>
  </div>
  <div class="proj-links">
    <a href="https://github.com/..." class="proj-link" target="_blank">GitHub →</a>
  </div>
</div>
```

### Changing the Accent Colour

Replace `--gold: #c9a84c` in `:root` with any hex value. All gold usages (`--gold`, `--gold-dim`, `--gold-glow`) will update automatically. The `rgba(201,168,76, ...)` values in the particle canvas JS will also need updating to match the new RGB values.

### Updating Hero Counters

Each counter uses three data attributes:

```html
<div class="stat-val" data-target="6" data-suffix="M+" data-float="false">0</div>
```

- `data-target` — the final number to count to
- `data-suffix` — appended after the number (e.g. `M+`, `%`, `K+`)
- `data-float="true"` — shows one decimal place (used for `99.9%`)

---

## Browser Support

Works in all modern browsers. No polyfills needed.

| Browser | Support |
|---|---|
| Chrome 80+ | ✅ Full |
| Firefox 75+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 80+ | ✅ Full |
| Mobile browsers | ✅ Responsive (cursor hidden on touch) |

> **Note:** The custom cursor is only visible on desktop/pointer devices. On mobile, the browser's native cursor behaviour applies. The `cursor: none` CSS is on `body` — you may want to add a `@media (hover: none)` query to re-enable it on touch screens if deploying for a broad audience.

---

## Performance Notes

- **Zero JS dependencies** — no React, no Vue, no jQuery
- **One external resource** — Google Fonts (3 font families, loaded async via `<link>`)
- **Canvas animation** — `requestAnimationFrame` loop with 80 particles. CPU-friendly at ~0.5ms/frame on modern hardware
- **IntersectionObserver** — used for both scroll reveal and counter animation. Fires once per element then `unobserve()` is called
- **No layout thrashing** — cursor position updates only `style.left` and `style.top` (CSS `top`/`left` with `transform: translate(-50%,-50%)` for centering). The ring uses `rAF` lerp, not a CSS transition that would fight the JS

---

## Content Sources

This portfolio was built using content from three sources:

| Source | Content |
|---|---|
| **Resume** (PDF) | Work experience bullets, technical skills, education, achievements |
| **Original portfolio** ([vercel.app](https://portfolio-vishnu-kumar.vercel.app/)) | College internships (NowOrNever, Decodr, Hozo), early projects |
| **LinkedIn** ([/in/vish1811](https://linkedin.com/in/vish1811)) | 6M users / 95M orders scale figures, SIH 2024 finalist, GitHub Constellation, podcast feature, RockStar Award 2nd year |

---

## Credits

Designed and coded by **Vishnu Kumar**.

Typography: [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) · [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) · [DM Sans](https://fonts.google.com/specimen/DM+Sans) via Google Fonts.

Design aesthetic inspired by editorial magazine layouts and the "Engineering Noir" visual language — deep blacks, warm gold, cinematic type scale.

---

## Contact

- **Email:** [vishnukumar.sde@gmail.com](mailto:vishnukumar.sde@gmail.com)
- **LinkedIn:** [linkedin.com/in/vish1811](https://linkedin.com/in/vish1811)
- **GitHub:** [github.com/vish1811](https://github.com/vish1811)
- **LeetCode:** [leetcode.com/vish1811](https://leetcode.com/vish1811) — Rating 1920, Top 5%

---

*Open to Senior SDE-2 / Staff Engineer roles at MAANG and high-growth product companies.*
