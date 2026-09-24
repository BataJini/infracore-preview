# Infracore — landing

Static landing page for **Infracore** (B2B IT supplier, Georgia), styled to the
Infracore Brand Guidelines: Deep Blue `#00007B` · Black `#000000` · Light Cyan `#8FE9FA`.
On screen the two blues are applied as slightly toned variants (client request, Sept 2026):
Deep Blue → `#273C91` (`--brand`), Light Cyan → `#B9E0F4` (`--cyan`), on an ice-blue page
canvas `#D2E6EF` (`--canvas`) with lighter section panels `#E8F1F7` (`--surface`). White is
reserved for cards, inputs and the modal. All of it lives in the `:root` tokens in `styles.css`.

Plain **HTML + CSS + a little vanilla JS** — no build step, no framework.

## Structure
```
index.html              — the page (inline SVG sprite at the top of <body>:
                          #ic-logo = full lockup, #ic-mark = symbol)
styles.css              — all styles (brand tokens + components)
assets/
  favicon.svg           — Deep Blue tile + white symbol (also favicon-32.png,
                          apple-touch-icon.png, icon-192.png, icon-512.png)
  infracore-logo.svg    — lockup (symbol + INFRACORE wordmark), currentColor
  infracore-symbol.svg  — symbol only, currentColor
  fonts/                — geist-mono-variable.woff2 (OFL) and
                          bpg-banner-supersquare.woff2 (typeface.ge, Georgian)
  logos/                — client logos for the marquee
  *.webp                — product renders, services photo
  pixel-canvas.js       — <pixel-canvas> Web Component (hover pixel wave)
.nojekyll               — serve folders as-is on GitHub Pages
```

## Brand system
- **Colours** live as tokens in `styles.css` (`--brand`, `--cyan`, tints).
- **Type**: Helvetica Neue for headings/body via the system stack
  (`"Helvetica Neue", Helvetica, Arial`) — it is a licensed font and is not
  embedded; Geist Mono (self-hosted) for eyebrows, labels and buttons;
  BPG Banner SuperSquare (self-hosted) drives the page in Georgian (KA) mode.
- **Logo / favicon**: vectors extracted from the brand-guidelines Illustrator
  file; header, hero and footer reference the sprite with `<use>`.

## Run locally
Open `index.html` in a browser, or serve the folder:
```bash
npx serve .
# or
python -m http.server 8080
```

## Deploy (GitHub Pages)
Settings → Pages → Source: **Deploy from a branch** → `main` / root.
The site is fully static, so it works as-is.

## Sections
Header (frosted on scroll) · Hero (Light Cyan banner, Deep Blue symbol) · Our Clients
marquee · product cards (sticky panels, alternating Light Cyan / Deep Blue) · how-we-work
stepper · why (Deep Blue integration node-graph with `<pixel-canvas>` wave) · services
(bento, white cards) · footer with CTA · EN/KA language switch.
