# Portfolio — CLAUDE.md

This file gives Claude Code full context about this project so you can continue development seamlessly.

---

## Project

Personal portfolio website for **Denys Bohatyrchuk**, Senior React / React Native Engineer.

- **Framework**: Astro (static site, no JS framework)
- **Styling**: Plain CSS with CSS variables (no Tailwind, no preprocessor)
- **Fonts**: DM Serif Display (headings) · DM Sans (body) · DM Mono (labels/code) — loaded from Google Fonts
- **Deploy target**: Vercel
- **Intended domain**: e.g. `bohatyrchuk.dev`

---

## File structure

```
portfolio/
├── src/
│   ├── components/
│   │   ├── Nav.astro          # Fixed top nav with blur, links to sections
│   │   ├── Hero.astro         # Full-height hero, animated availability badge
│   │   ├── Experience.astro   # All 6 jobs, grid layout (date col + content col)
│   │   ├── Projects.astro     # 4 featured project cards in a bordered grid
│   │   ├── Skills.astro       # 6 skill groups in a two-column list layout
│   │   └── Contact.astro      # Contact section + footer
│   ├── layouts/
│   │   └── Layout.astro       # Base HTML shell, loads global.css
│   ├── pages/
│   │   └── index.astro        # Assembles all components, single page
│   └── styles/
│       └── global.css         # All CSS variables, reset, base styles
├── public/
│   └── favicon.svg
├── astro.config.mjs
├── package.json
└── README.md                  # Deploy instructions
```

---

## Design system

All colors are CSS variables in `src/styles/global.css`. The site supports both dark and light themes by swapping the `:root` block — no other files need to change.

### Current theme (dark)

```css
:root {
  --bg: #0c0c0b;
  --bg-2: #141413;
  --bg-3: #1c1c1a;
  --border: rgba(255,255,255,0.08);
  --border-strong: rgba(255,255,255,0.15);
  --text: #f0ede8;
  --text-2: #a09d96;
  --text-3: #5c5a55;
  --accent: #d4a853;
  --accent-dim: rgba(212,168,83,0.12);
}
```

### Light theme alternative

```css
:root {
  --bg: #faf9f7;
  --bg-2: #f3f1ed;
  --bg-3: #ebe8e2;
  --border: rgba(0,0,0,0.08);
  --border-strong: rgba(0,0,0,0.15);
  --text: #1a1916;
  --text-2: #6b6860;
  --text-3: #a8a49d;
  --accent: #b8860b;
  --accent-dim: rgba(184,134,11,0.10);
}
```

If switching to light, also update the nav backdrop in `Nav.astro`:
```css
/* dark */  background: rgba(12,12,11,0.85);
/* light */ background: rgba(250,249,247,0.85);
```

---

## Content — what's already populated

All content was generated from Denys's CV. To update any section, edit the data arrays at the top of each component (inside the `---` frontmatter block).

### Experience (`Experience.astro`)
Array: `jobs[]` — 6 entries:
1. ICEO — BeOne (Jul 2025 – present)
2. Startupsoft — Tow4Tech (Oct 2023 – Jul 2025)
3. NDA — Public Security App (Apr – Oct 2023)
4. Geniusee — Argo Fintech (Apr 2022 – Apr 2023)
5. Velas Network AG — BitOrbit (Dec 2020 – Apr 2022)
6. Andersen Lab — First Bank of Nigeria (Nov 2019 – Dec 2020)

### Projects (`Projects.astro`)
Array: `projects[]` — 4 entries: BeOne, Tow4Tech, BitOrbit, Argo.

### Skills (`Skills.astro`)
Array: `groups[]` — 6 groups: Core, State & Data, Native, Blockchain, Testing & Tooling, Maps & Real-time.

---

## Pending TODOs

- [ ] Replace GitHub link placeholder (`href="https://github.com"`) in `Nav.astro` and `Contact.astro` with real URL
- [ ] Replace LinkedIn link placeholder (`href="https://linkedin.com"`) in `Contact.astro` with real URL
- [ ] Optionally add a photo to `public/photo.jpg` and reference it in `Hero.astro`
- [ ] Set real domain in `astro.config.mjs` → `site: 'https://yourdomain.dev'`
- [ ] Set up Vercel project and connect GitHub repo

---

## How to run

```bash
npm install
npm run dev       # localhost:4321
npm run build     # production build → dist/
npm run preview   # preview production build locally
```

## How to deploy

1. Push to GitHub
2. Import repo on vercel.com → framework: Astro (auto-detected)
3. Click Deploy

---

## Conversation history summary

This project was built in a single Claude chat session on claude.ai. Key decisions made:

- Chose **Astro over HTML** for maintainability and Vercel compatibility
- Chose **empty template** (`--template empty`) when running `npm create astro@latest`
- Dark editorial aesthetic with gold accent — inspired by refined print design
- **No Tailwind** — plain CSS with variables for simplicity and portability
- Light theme is a CSS-variable swap only, no structural changes needed

The full portfolio was generated from Denys's CV PDF in one pass. All content is accurate as of June 2026.
