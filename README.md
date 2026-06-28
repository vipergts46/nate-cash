# nate.cash

Personal site for Nate Cash. Static Astro + Tailwind v4, deployed via Cloudflare Pages on `git push`. Built from the Jebb Graff 2021 brand mood board.

## Stack

- **Astro 7** (static output)
- **Tailwind v4** (CSS-first theme tokens in `src/styles/global.css`)
- **Fonts:** Outfit (display) + Inter (body), loaded from Google Fonts
- **Hosting:** Cloudflare Pages
- **Domain:** `nate.cash` (registered at GoDaddy, DNS still at GoDaddy for v1)

## Local dev

```sh
npm install
npm run dev        # localhost:4321
npm run build      # static output to ./dist/
npm run preview    # preview the built site
```

Node ≥ 22.12 (the installed `v26.x` is fine).

## Project layout

```
src/
├── components/     # Header.astro, Footer.astro
├── layouts/        # Base.astro — shared shell, meta, dark mode
├── pages/
│   ├── index.astro          # /
│   ├── about.astro          # /about
│   ├── contact.astro        # /contact
│   ├── 404.astro            # custom 404 with "wonder & wander" easter egg
│   └── macropilot/
│       ├── index.astro      # /macropilot
│       ├── privacy.astro    # /macropilot/privacy (required by Apple + Google)
│       └── support.astro    # /macropilot/support (required by Apple)
└── styles/
    └── global.css           # @theme tokens (palette + fonts)
public/
└── favicon.svg              # NC monogram + accent dot
```

## Design tokens

All in `src/styles/global.css`. Edit there to change palette/fonts globally.

| Token           | Hex       | Role                                  |
| --------------- | --------- | ------------------------------------- |
| `--color-bg`        | `#F7FFF7` | Page background                       |
| `--color-ink`       | `#2B2B2B` | Body text, headings                   |
| `--color-primary`   | `#69A2B0` | Links, primary accents                |
| `--color-secondary` | `#7E8B4A` | Olive (lightened sage) — section dividers, badges, callouts |
| `--color-accent`    | `#D5602B` | Hover, CTA punch, MacroPilot highlight |
| `--color-muted`     | `#6B7068` | Secondary text                        |

Dark mode honors `prefers-color-scheme` and inverts bg/ink.

> Olive was lightened from the mood-board original (`#4B5320` → `#7E8B4A`) for better readability on the dark surface. Orange (`#D5602B`) is a stand-in for the orange the mood board mislabeled as `#4B5320`.

## Editing content

- **Bio + tagline:** `src/pages/index.astro` (hero) and `src/pages/about.astro` (long form)
- **MacroPilot copy:** `src/pages/macropilot/*.astro`
- **Privacy policy:** `src/pages/macropilot/privacy.astro` — currently marked as a placeholder. Replace before public app launch.
- **Header nav links:** `src/components/Header.astro`
- **Footer + LinkedIn link:** `src/components/Footer.astro`

## Adding a blog post later

Reserved for v2. Plan: Astro content collection at `src/content/notes/*.md`, route `/notes/[slug]`.

## Deploy

Hooked to **Cloudflare Pages**. Push to `main` → auto-deploys.

- Build cmd: `npm run build`
- Output dir: `dist/`
- Custom domain: `nate.cash` (DNS at GoDaddy points to Cloudflare Pages targets)
- Email (`me@nate.cash → vipergts46@gmail.com`) stays on GoDaddy forwarding — its MX records were preserved when DNS was updated.

## Brand voice (from mood board v01)

- smart not pretentious
- confident not cocky
- soothing not obnoxious
- courageous not fearful
- adventurous not careless

> Wonder & wander. Not scared & lost.
