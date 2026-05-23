# ownEvo — Brand & Design Guidelines

This document codifies the brand and design system for ownEvo. It is the source
of truth for the public site and any external surface (decks, OG images, social
avatars, partner collateral). When in doubt, this file wins over local choices.

---

## 1. Brand essence

**ownEvo** is the platform for **core agents** — agents that run on the
workflows that define how an enterprise competes, owned and improved entirely
by the customer.

Three pillars, in priority order:

1. **Ownership** — sovereignty over the agent, the model, the eval set, and
   the institutional knowledge that compounds inside it. The customer purchases,
   they don't rent.
2. **Evolution** — a closed improvement loop on the customer's own data. Every
   failure becomes an eval case. The agent at day 365 is measurably better than
   day 1.
3. **Ambient** — agents run continuously, on their own schedule, surfacing only
   what genuinely needs a human decision.

**Audience** — domain experts and the enterprises they run: supply chain VPs,
chief risk officers, chief medical officers, finance leaders. Not developers.
Not consumer users. Not "AI-curious."

**Voice** — sovereign, institutional, production-first. Closer to a trusted
infrastructure vendor than a creative-tool SaaS. We measure success in business
outcomes, not benchmark numbers.

---

## 2. Naming & wordmark

### Spelling

- **`ownEvo`** is the canonical brand spelling — lowercase `own`, capital `E`.
- The italic on `Evo` is a typographic device used for emphasis in headlines
  and the nav wordmark. It is **not** mandatory in body copy.
- In running text where italics aren't supported (terminal output, plain-text
  email), use `ownEvo`.
- Domain: `ownevo.ai`.

### Don't

- ❌ `OwnEvo`, `OWNEVO`, `Own Evo`, `OwnEVO`, `ownevo` (in headings).
- ❌ Don't bold `Evo`. Don't underline. Italic is the only emphasis treatment.
- ❌ Don't translate or localize the wordmark.

---

## 3. Logo system

ownEvo has two complementary brand assets that serve different jobs:

### 3.1 Primary — CSS text wordmark

Used everywhere the brand appears in HTML (nav, headings, footer, body). It is
the **default** brand expression on the web and should not be replaced by an
image.

```html
<span class="logo-own">own</span><span class="logo-evo">Evo</span>
```

```css
.logo-own { color: var(--grey-300); }
.logo-evo { color: var(--accent); font-style: italic; }
```

Properties:
- Family: `Outfit`, weight 600, letter-spacing -0.03em.
- `own` in `--grey-300` at UI sizes (nav, footer, body, ≤ ~48px).
- `Evo` in `--accent` italic.
- Scales infinitely; accessible; SEO-friendly.

**Display sizes (~96px and up — video title cards, OG images, posters,
hero treatments).** At small UI sizes, `#475569` reads as a confident
near-black against white because antialiasing concentrates the color
in tight strokes. At display sizes the same hex reads as washed-out
grey — the strokes are wider, so the perceived ink density drops. For
display-scale wordmarks, switch `own` to `--ink` (`#0B0E14`) so the
wordmark matches the optical weight viewers expect from the small-size
nav. `Evo` stays `--accent` italic at every size.

### 3.2 Mark — shield icon (`logo-shield.svg`)

A solid blue shield containing a dark closed ring with a small upward
triangle floating above it. Combines both pillars in one glyph:

- **Shield** = ownership / sovereignty / institutional protection.
- **Closed ring** = the improvement loop, continuous and self-contained.
- **Triangle above** = a claim of ownership planted on top of the loop —
  the loop is yours.

Together, the mark reads as *"Own the loop"* — the brand's tagline rendered
into a single glyph: a sovereign, continuously running, owned-by-you loop.

Used **only** where the text wordmark physically can't render at the required
size or square aspect ratio:

| Surface | File | Size |
|---|---|---|
| Browser favicon (tab) | `favicon.ico`, `favicon-32.png` | 32×32 |
| iOS home-screen icon | `apple-touch-icon.png` | 180×180 |
| Social avatars (GitHub, Slack, LinkedIn) | derive from `logo-shield.svg` | 400×400 |
| OG image / share preview | lockup (mark + wordmark) | 1200×630 |

Two SVG variants are checked in:

- `logo-shield.svg` — **filled** (blue shield, dark ring + triangle above).
  Use for favicons, app icons, and any context with a non-brand background.
- `logo-shield-outline.svg` — **outline only** with `currentColor`. Use inline
  on the site (nav, footer) so it adopts the site's accent color via CSS.

### 3.3 Lockup (TBD)

A horizontal lockup of mark + wordmark for OG images, slide footers, and
business cards is not yet checked in. When created, it goes in
`logo-lockup.svg` with the mark on the left, ¼ x-height of padding, then the
wordmark in the same `Outfit 600` typography.

### Don't

- ❌ Don't recolor the shield with magenta, orange, multi-stop gradients, or
  rainbow palettes — those clash with the site palette and signal "consumer
  AI tool."
- ❌ Don't replace the CSS text wordmark in the nav with an image.
- ❌ Don't use the shield without sufficient padding (≥ ½ shield width).
- ❌ Don't place the mark on busy photographic backgrounds without a flat
  surface beneath.

---

## 4. Color

### Primitives (HEX)

| Token | Value | Role |
|---|---|---|
| `--bg` | `#ffffff` | Page background, primary surface |
| `--surface` | `#f8fafc` | Cards, nav (scrolled) |
| `--surface-2` | `#f1f5f9` | Elevated surface (core column, inset blocks) |
| `--border` | `#e2e8f0` | Default divider, card border |
| `--border-light` | `#cbd5e1` | Hover / focus border, subtle separator |
| `--accent` | `#3b82f6` | The single accent — italic Evo, links, primary CTAs, icons |
| `--accent-hover` | `#2563eb` | Hover state of `--accent` only |
| `--accent-dim` | `#3b82f60d` | Pull-quote backgrounds, faint accent fills |
| `--accent-glow` | `#3b82f614` | Hero radial glow / soft accent overlay |
| `--accent-muted` | `rgba(59,130,246,0.10)` | Icon backgrounds, soft fills |
| `--white` | `#0f172a` | Headlines, primary copy (semantic name preserved; value flips per theme) |
| `--grey-100` | `#1e293b` | Secondary copy |
| `--grey-200` | `#334155` | Lists, supporting copy |
| `--grey-300` | `#475569` | Body text default; the `own` of the wordmark at UI sizes (display sizes use `--ink` instead — see §3.1) |
| `--grey-500` | `#64748b` | Captions, fine print |
| `--grey-700` | `#94a3b8` | Faintest readable copy, footer text |
| `--grey-900` | `#cbd5e1` | Reserved (currently unused on light theme) |
| `--green` | `#059669` | "Good" / `ownEvo alternative` semantic |
| `--red` | `#dc2626` | "Bad" / `the current deal` semantic |

### Rules

- **One accent.** `#3b82f6` is the only saturated color on the site. Do not
  introduce purple, orange, magenta, or teal as additional accents.
- **Green and red are semantic-only** — used for problem/solution juxtaposition
  and validation states. Never decorative.
- **Backgrounds are light by default** — institutional white on grey-blue
  scale. A dark variant is not currently shipped; design separately if needed.
- **Borders are flat and tight.** No glowing borders except the hero glow and
  the primary CTA hover.

---

## 5. Typography

### Families

- **`Outfit`** (Google Fonts) — display + sans. Weights loaded: 200, 300, 400,
  500, 600, 700. Used for everything that is not technical detail.
- **`JetBrains Mono`** (Google Fonts) — monospace. Weights: 300, 400, 500.
  Used **only** for: section labels, hero terminal feed, proof-card details,
  footer, and any technical/data fragment.

### Scale

| Use | Family | Size | Weight | Letter-spacing |
|---|---|---|---|---|
| Hero headline | Outfit | `clamp(2.6rem, 6vw, 4.8rem)` | 700 | -0.04em |
| Section heading | Outfit | `clamp(1.8rem, 3.5vw, 2.8rem)` | 700 | -0.03em |
| Sub headline (h3 in cards) | Outfit | 1.0–1.05rem | 600 | -0.02em |
| Body | Outfit | 1.05rem | 400 | normal |
| Small body / card body | Outfit | 0.85–0.88rem | 400 | normal |
| Section label | JetBrains Mono | 0.58rem | 400 | 0.22em UPPERCASE |
| Card label | JetBrains Mono | 0.56rem | 400 | 0.16–0.20em UPPERCASE |
| Footer / fine print | JetBrains Mono | 0.52–0.54rem | 400 | 0.08–0.10em UPPERCASE |

### Rules

- Headlines use `<em>` to italicize the punch word in the brand accent color
  (e.g., *Nobody else's.* — the `<em>` carries `font-style: italic; color:
  var(--accent);`).
- Body line-height: 1.6–1.7. Card body line-height: 1.5–1.65.
- Never set a fixed pixel size on headlines — always `clamp()` for fluid scale.
- Never set a font-weight below 400 on body copy.

---

## 6. Layout & spacing

- **Section width:** `max-width: 1080px`, padded `padding: 6rem 2rem`.
- **Headline width:** ≤ 800px (hero) or 640px (section).
- **Body width:** ≤ 580px.
- **CTA copy width:** ≤ 480px.
- **Vertical rhythm:** sections separated by either a 6rem internal gap or a
  `<hr class="section-rule">` divider.
- **Decorative grid background:** 64px dot grid, ≤ 2.5% opacity, masked by a
  radial gradient centered at `50% 30%`.
- **Border radius:** `2px–4px` only. ownEvo is geometric and precise; no pills,
  no `border-radius: 999px`. The one exception is the feed-dot (semaphore
  circles) at 50%.

---

## 7. Iconography

- **Library:** custom inline SVG. No icon font, no Lucide/Heroicons import.
- **Stroke:** 1.5px on a 24×24 viewBox.
- **Color:** `currentColor` so icons inherit the surrounding text color.
- **Fills:** none. Outline-only (with the one shield-mark exception, which is a
  brand asset, not a UI icon).
- **Inline usage:** `<svg width="14|16|18|20" ...>` depending on context.
- **Caps & joins:** `stroke-linecap="round"`, `stroke-linejoin="round"`.

If you need an icon that doesn't exist yet, draw it on a 24×24 grid with the
above rules.

---

## 8. Components reference

These are the component patterns currently used. Reuse them; do not invent
parallel patterns that overlap.

| Component | Where defined | Notes |
|---|---|---|
| `nav` (transparent → frosted on scroll) | `index.html` | `.scrolled` class added > 40px |
| `.btn-primary` | `index.html` | Solid accent, dark text, hover glow |
| `.btn-ghost` | `index.html` | Border-only, brightens on hover |
| `.problem-card.bad` / `.problem-card.good` | `index.html` | Red/green semantic borders |
| `.cvo-grid` (Core vs Ops) | `index.html` | Two-column compare table |
| `.loop-step` | `index.html` | Numbered steps with auto-cycling `.active` opacity |
| `.proof-card` | `index.html` | Stat + label + mono detail |
| `.sov-card` / `.persona-card` | `index.html` | 3-up grid, surface bg, accent icon block |
| `.pullquote` | `index.html` | Left accent border, accent-dim background |
| `.hero-feed` | `index.html` | Mock terminal with auto-typing log |

---

## 9. Motion

- **Easing:** `cubic-bezier(0.16, 1, 0.3, 1)` for entrance animations.
- **Hover transitions:** `0.15s–0.3s` linear or `ease-out`.
- **Hero entrance:** staggered `up` keyframe at 0.1s / 0.2s / 0.35s / 0.5s /
  0.65s offsets, 0.6–0.7s duration.
- **Loop steps:** auto-advance every 2.2s; opacity-only state change.
- **No bouncy springs, no parallax, no scroll-jacking.** ownEvo's motion is
  measured and intentional, not flashy.

---

## 10. Voice & messaging

### Headlines

- One short sentence + a punch word in italic accent. Examples already in use:
  - *Your agents. Your edge.* **Nobody else's.**
  - *Ops agents are a commodity.* **Core agents are your identity.**
  - *Run anywhere. Own everything.* **Lock in to nothing.**

### Body

- Short paragraphs. Concrete examples from supply chain, finance, healthcare,
  legal — never abstract AI hype.
- Prefer the concrete failure or decision over the abstract category.
- Reference real numbers when proving (`+50.7%`, `95.2%`, `200 events`, etc.)
  rather than relative claims.

### Forbidden

- ❌ Exclamation marks (single or multiple).
- ❌ "Revolutionary," "game-changing," "AI-powered," "next-gen," "leverage."
- ❌ Emoji in copy.
- ❌ "User" — say "domain expert," "supply chain VP," "underwriter," etc.
- ❌ Capital-A "Agent" or "AI" except at sentence start.

### Approved phrases (canon)

- *Own the loop. Own the edge.*
- *Own your AI evolution.*
- *Core agents, not ops agents.*
- *The agent that runs today is measurably better than six months ago.*
- *Failures are captured, clustered, and converted into eval cases.*
- *No signal leaves your walls.*

---

## 11. File inventory

```
www/
├── BRAND.md                  ← this file
├── index.html                ← the site
├── logo-shield.svg           ← filled mark, brand colors hardcoded
├── logo-shield-outline.svg   ← outline mark, currentColor (inline use)
├── favicon.ico               ← 32×32 ICO, generated from logo-shield.svg
├── favicon-32.png            ← 32×32 PNG, generated from logo-shield.svg
├── apple-touch-icon.png      ← 180×180 PNG, generated from logo-shield.svg
├── CNAME
└── .bak/                     ← previous placeholder favicons
```

To regenerate favicons after editing `logo-shield.svg`:

```bash
cd www
gdk-pixbuf-thumbnailer -s 180 logo-shield.svg apple-touch-icon.png
gdk-pixbuf-thumbnailer -s 32  logo-shield.svg favicon-32.png
ffmpeg -y -i favicon-32.png favicon.ico
```

---

## 12. Open questions / future work

- **Dark-mode variant** — not currently shipped; design separately if needed.
- **Lockup SVG** — needed for OG images, slide footers, and printed collateral.
- **Brand mark variants** — single-color knockout (white on accent), reverse
  (accent on white) versions of `logo-shield.svg` for partner co-branding.
- **OG image** — once the lockup exists, build a 1200×630 `og.png` so social
  share cards stop falling back to the favicon.
- **Print specs** — CMYK equivalents of `--accent`, `--bg`, `--white` for any
  printed material.
