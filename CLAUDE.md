# CLAUDE.md — ownEvo www/

Orientation for any future Claude instance working in this directory.

This is the **public marketing site** for ownEvo (`ownevo.ai`). It is a single
static HTML page with no build step. If you are editing it, the work usually
falls into one of three buckets: tightening copy, adjusting design, or wiring
in a new asset (favicon, OG image, lockup). Read this file plus `BRAND.md`
before changing anything user-visible.

---

## 1. The product, in one paragraph

**ownEvo is the platform for *core agents*** — agents that run on the
workflows that define how an enterprise competes (demand forecasting at SKU
granularity, credit model recalibration through the cycle, clinical trial
design, supplier negotiation playbooks). The product captures every production
failure as a clustered eval case, regression-tests every proposed improvement
against every prior fix, and lets a domain expert (not a developer) approve
changes in plain language. The customer owns the model choice, the eval set,
the improvement history, and the institutional knowledge that compounds inside
the system. Run anywhere — cloud, hybrid, or fully local.

Domain: `ownevo.ai`. The site at `www/index.html` is the customer-facing front
door; pitch + manifesto live in `../../startup_mono/docs/`.

---

## 2. Company & audience

- **Stage:** Pre-seed / YC application track (W26 cycle context).
- **Brand spelling:** `ownEvo` — lowercase `own`, capital `E`. Italic on `Evo`
  is a typographic device (used in headlines and the wordmark), not mandatory
  in body copy. See `BRAND.md` §2.
- **Tagline canon:** *Own the loop. Own the edge.* / *Own your AI evolution.*
- **Audience the site is written for:** supply chain VPs, chief risk officers,
  chief medical officers, finance leaders. Domain experts and the enterprises
  they run. **Not developers, not consumer users, not "AI-curious" buyers.**
- **Buyer signals to lean into:** "I have a workflow that encodes 20 years of
  decisions and the people who built it are retiring." "I won't share my
  proprietary signal with any vendor." "I need this to keep getting better
  every quarter without rebuilding."

---

## 3. The thesis (the manifesto in five claims)

Read the full document at
`../../startup_mono/docs/pitch/ownevo-manifesto.md`. The five load-bearing
claims:

1. **The model race is over for enterprise.** Models are capable enough for
   production workloads. The bottleneck has shifted from model quality to the
   institutional knowledge running on top of it.
2. **The "data-for-improvement" bargain is hostile.** Most platforms ingest
   your operational failures and use them to improve their model for everyone
   — including your competitors. *You paid for the failure. They captured the
   lesson.*
3. **Ops agents vs. core agents is the only distinction that matters.** Ops
   agents (HR, sales, expense) are commodity and interchangeable. Core agents
   encode how a company actually competes. Core agents *cannot* be bought; they
   must be built and owned.
4. **Static agents degrade.** An agent that isn't actively improving is falling
   behind, not staying even. The world drifts. Memory corruption compounds.
   The only defense is a continuous improvement loop with a living eval set.
5. **Continual learning is a data + eval problem, not a research problem.**
   The training signal that improves your core agent is your production
   history. It cannot exist at a model lab. It must be captured in place,
   evaluated in place, and owned in place.

Sub-themes worth remembering:
- **Ambient operation:** the agent's value is proportional to how much it does
  without being asked. *"The agent that runs while you sleep, captures what
  changed, and has a prioritized briefing ready when you open your laptop."*
- **Plain-language approval:** the domain expert reads the proposed
  improvement and approves or rejects it. The developer is not in the loop.
- **Three pillars of ownership:** model independence · local operation ·
  portability (export everything in an open format).

---

## 4. The canonical phrases

Pulled from the manifesto, landing copy, and pitch docs. These have been
through review; reuse rather than reinvent:

- *Own the loop. Own the edge.*
- *Own your AI evolution.*
- *Models are ready. Now own the intelligence.*
- *Your agents. Your edge. Nobody else's.*
- *Ops agents are a commodity. Core agents are your identity.*
- *Deploy once. Improve forever. Regress never.*
- *You paid for the failure. They captured the lesson.*
- *No step forward that loses a step already gained.* (regression gate)
- *The model is a commodity. The improvement loop is the moat.*
- *No signal leaves your walls.*
- *When the person who built that workflow retires — what happens to what
  they knew?* (the closing question of the manifesto)

---

## 5. The current site (what's actually shipped)

`index.html` is one page, ~1000 lines, structured as:

| Section | Purpose | Anchor |
|---|---|---|
| Nav (sticky, frosted on scroll) | Brand wordmark + "Talk to us" CTA | — |
| Hero | Headline + subhead + dual CTA + auto-typing terminal feed | `#hero` |
| Problem | "The data-for-improvement bargain you didn't agree to" — bad/good card pair + pull-quote | `#problem` |
| Use Cases | Three vertical deep-dives: Supply Chain · Finance & Insurance · Healthcare & Pharma | `#use-cases` |
| How It Works (The Loop) | 6-step auto-cycling loop | `#how-it-works` |
| IK Problem | "The most valuable things in your business aren't in any document." — institutional knowledge close | `#ik-problem` |
| Sovereignty | Three cards: any model · local if you need it · export any time | `#sovereignty` |
| Final CTA | "Which workflow defines your business?" | `#contact` |
| Footer | Copyright + privacy/security/contact stubs | — |

**Removed sections** (notes + restoration criteria in `../ownevo_docs/pitch/ownevo-landing-copy.md`):
- Core vs. Ops — redundant with Use Cases once vertical deep-dives are on the page
- Who It's For — redundant with Use Cases; same three verticals in shallower form
- Proof / Validation — three stat cards not yet manually validated; wrong audience framing

**Single CTA destination:** all `Talk to us` / `Tell us about your core
workflow` buttons currently route to `https://forms.gle/EgVikAcwzQwXszyUA`. If
that ever changes, search-and-replace across `index.html`.

---

## 6. Alternate landing-page directions (not yet shipped)

These come from `../ownevo_docs/pitch/ideas-scratchpad.md` (formerly `ownevo-landing-ideas.md`, now merged into the scratchpad). They exist as living alternatives. If the current frame underperforms or a specific audience needs a different opening, pull from here:

**Hero variants on file (currently shipping option close to A):**

- **A — Ownership:** *Your agents. Your data. Your edge.* → "Core agents for
  the workflows that define your business — owned by you, improving with you,
  running anywhere."
- **B — Post-AGI framing:** *Models are ready. Now own the intelligence.* →
  "The post-AGI competitive advantage isn't the model — it's who owns the
  learning layer on top of it."
- **C — Evolution:** *Deploy once. Improve forever.* → "Agents that capture
  your institutional knowledge, grow their own eval sets, and get measurably
  better every workflow."
- **D — Sovereignty (anti-lab):** *The agent that knows your business. Owned
  by your business.* → "No hostage to LLM labs. No data-for-improvement
  bargain. Run local if you want. Port any model."
- **E — Core vs. Ops:** *Not an ops agent. A core agent.* → "HR and sales
  automation are table stakes. We're for the workflows that define who you
  are."

**Section ideas not yet on the page (worth considering):**

- **Visual loop diagram** — the 6-step loop currently uses text + numbers.
  An animated/interactive version was sketched in `ideas-scratchpad.md`.
- **Vertical-specific landing variants** — supply-chain-focused, finance,
  healthcare. The current page has a Use Cases section covering all three.
  Consider spinning vertical landings if/when one buyer type dominates pipeline.
- **Competitive contrast table** — `ideas-scratchpad.md` has a 6-row "What
  others offer / What ownEvo offers" table that is *not* on the page. It was
  held back as too direct.
- **Proof / Validation** — removed May 2026; can be restored once numbers are
  manually validated. See removal note in `../ownevo_docs/pitch/ownevo-landing-copy.md`.

---

## 7. Voice & writing rules (enforce when editing copy)

From `BRAND.md` §10 — the short version:

- One short headline + a punch word in italic accent (`<em>`) — that's the
  pattern. Don't break it.
- Concrete examples from supply chain, finance, healthcare, legal. Never
  abstract AI hype.
- Real numbers when proving. Relative claims are weaker.
- **Forbidden:** exclamation marks. "Revolutionary," "game-changing,"
  "AI-powered," "next-gen," "leverage." Emoji. The word "user" (use "domain
  expert," "supply chain VP," "underwriter").
- Capital-A "Agent" or "AI" only at sentence start.

---

## 8. Brand & design pointer

`BRAND.md` (in this directory) is the canonical spec for color tokens, type
scale, components, motion, and the logo system. **Read it before editing any
visual element.** If you're tempted to introduce a new color, a new font, or a
new component pattern, the answer is almost always to reuse what's already
there.

The single accent color is `#3b82f6` (Tailwind blue-500). The brand mark is the shield
SVG (ownership = shield silhouette + ownership-flag triangle planted on top of
the inner loop, evolution = the closed ring inside the shield). The text
wordmark in the nav is the **primary** brand expression on the web; the
shield is supporting it, not replacing it.

---

## 9. File map

```
www/
├── CLAUDE.md                 ← this file (orientation for future Claude)
├── BRAND.md                  ← canonical brand & design spec
├── index.html                ← the entire site (HTML + inline CSS + inline JS)
├── logo-shield.svg           ← filled brand mark (favicons + app icons)
├── logo-shield-outline.svg   ← currentColor outline (inline web use)
├── favicon.ico               ← 32×32 ICO, generated from logo-shield.svg
├── favicon-32.png            ← 32×32 PNG
├── apple-touch-icon.png      ← 180×180 PNG
├── CNAME                     ← GitHub Pages custom domain (ownevo.ai)
├── .bak/                     ← previous placeholder favicons
└── .git/                     ← deployed via GitHub Pages
```

Adjacent context (outside this dir, but worth knowing):

- `../../startup_mono/docs/pitch/` — manifesto, landing-ideas, pitch lines.
- `../../startup_mono/docs/executive-summary.md` — company-level pitch.
- `../../startup_mono/docs/market/` — competitor analysis, customer playbook.

---

## 10. Editing conventions

- **No build step.** All CSS is inline in `<style>` and all JS is inline in
  `<script>` at the bottom of `index.html`. Don't introduce a bundler, a
  framework, or external stylesheets. The fonts are the only external
  dependency (Google Fonts: Outfit + JetBrains Mono).
- **Never replace the CSS text wordmark in the nav with an image.** It is the
  primary brand expression. The shield SVG already sits inline next to it.
- **Don't introduce a second accent color.** If you need to communicate
  hierarchy, use the existing grey scale or the semantic green/red.
- **Headlines must follow the italic-Evo / italic-punch-word pattern.** Wrap
  the punch word in `<em>` — the CSS already styles it as italic accent.
- **No emoji, no exclamation marks, no marketing-cliché vocabulary.** The
  voice is sovereign and institutional, closer to a trusted infrastructure
  vendor than a creative SaaS tool.
- **CTAs all route to the same Google Form** (currently
  `https://forms.gle/EgVikAcwzQwXszyUA`). Single source of intake.
- **Mobile breakpoints** at 768px and 500px are already defined. Verify any
  new layout block at those widths before shipping.

---

## 11. Useful commands

Regenerate the favicons after editing `logo-shield.svg`:

```bash
cd /Users/jit/code/ownevo/www
gdk-pixbuf-thumbnailer -s 180 logo-shield.svg apple-touch-icon.png
gdk-pixbuf-thumbnailer -s 32  logo-shield.svg favicon-32.png
ffmpeg -y -loglevel error -i favicon-32.png favicon.ico
```

Lint-check the HTML quickly (no formal linter wired up):

```bash
# Verify structure
python3 -c "from html.parser import HTMLParser; import sys; HTMLParser().feed(open('index.html').read()); print('ok')"
```

Preview locally:

```bash
python3 -m http.server -d /Users/jit/code/ownevo/www 8000
# open http://localhost:8000
```

---

## 12. Open follow-ups

Tracked here so they aren't lost. Cross-reference `BRAND.md` §12.

- **Logo lockup SVG** — horizontal mark + wordmark for OG images, slide
  footers, and printed collateral. Once it exists, generate a real
  1200×630 `og.png` and update the `og:image` / `twitter:image` meta tags
  (currently fall back to `apple-touch-icon.png`).
- **Dark-mode variant** — not currently shipped; requires a separate spec if needed.
- **Vertical landings** — supply-chain.html, finance.html, healthcare.html
  variants if/when one buyer type dominates pipeline.
- **Privacy / Security pages** — footer links currently `href="#"`. Should
  point to real pages once drafted.
- **Animated loop diagram** — sketched in `landing-ideas.md`, not built.
