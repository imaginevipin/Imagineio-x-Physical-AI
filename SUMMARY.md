# Project Summary — Imagineio Physical AI

> **For Claude:** Read this file at the start of every conversation to restore full project context. Update it after every significant decision, build, or iteration — especially before the user clears the chat.

---

## Project Identity

- **Client / Brand:** imagine.io
- **Project:** Physical AI (name TBD)
- **Design System:** Prism — tokens in `tokens.css`, fonts in `assets/fonts/`, logos in `assets/logos/`
- **Figma File:** [Imagine.io x Physical AI](https://www.figma.com/design/1aL836P4R3p09gOwE5TVQz/Imagine.io-x-Physical-AI?node-id=0-1) — primary design file for this project (fileKey: `1aL836P4R3p09gOwE5TVQz`)

---

## Model Usage

| Task Type | Model | When to Use |
|-----------|-------|-------------|
| Quick answers, small edits | Haiku (`claude-haiku-4-5-20251001`) | Fast lookups, minor copy changes, simple questions |
| Most work | Sonnet (`claude-sonnet-4-6`) | UI builds, standard coding, iteration |
| Deep research, complex tasks | Opus (`claude-opus-4-6`) | Architecture decisions, advanced coding, research |

---

## Outputs Structure

All deliverables go in `outputs/` as flat versioned files — naming convention: `[page-name]-v[N].html` (e.g. `homepage-v5.html`). Never overwrite — always create a new version file.

### CSS / HTML Separation (v5 onwards)

- HTML → `outputs/homepage-vN.html`
- CSS → `css/homepage-vN.css` (project root, outside `outputs/`)
- HTML links tokens: `<link rel="stylesheet" href="../tokens.css">`
- HTML links page CSS: `<link rel="stylesheet" href="../css/homepage-vN.css">`
- No `<style>` blocks inside HTML files from v5 onwards — all styles in the paired `.css` file

---

## What We're Planning

Building an imagine.io website for the Physical AI / robotics data market — visually and narratively similar to **physicl.ai** (reference), adapted to Prism Design System.

Full plan is in `PLAN.md`. Summary of the plan:
- 4 pages: Homepage, /robotics, /foundation-models, /company
- Homepage has 14 sections following the same "Hook → Depth → Proof → CTA" arc as physicl.ai
- Key UI: marquee carousels, pipeline steps, code demo, stat blocks, use case split, vertical asset validation scroll
- Animations: pure CSS + vanilla JS (no GSAP dependency)
- Build order: Homepage static (v1) → Homepage animated (v2) → inner pages

See `PLAN.md` for the full UX/UI research breakdown, component inventory, and content checklist.
See `research/design-reference.md` for the living visual design reference — updated every time we do a new round of analysis from any reference site.

---

## Decisions Made

| Date | Decision | Reason |
|------|----------|--------|
| 2026-03-23 | Project initialized with Prism Design System | imagine.io project — full token/font/logo setup |
| 2026-03-23 | Outputs folder with versioned variations | Keep all iterations accessible, never overwrite |
| 2026-03-23 | SUMMARY.md as persistent context file | Claude loses context when chat is cleared; this bridges the gap |
| 2026-03-23 | Three-tier model usage (Haiku / Sonnet / Opus) | Cost and capability matching |
| 2026-03-23 | Reference site: physicl.ai — full UX/UI research done | Basis for page structure, narrative arc, components |
| 2026-03-23 | Homepage has 14 sections, build order defined in PLAN.md | Phase 1 = static homepage, Phase 2 = animated |
| 2026-03-23 | Multi-page website confirmed (separate HTML files per page) | User confirmed; homepage first, inner pages after |
| 2026-03-23 | Real copy + real logos in v1; black placeholders for images | User confirmed; no lorem ipsum |
| 2026-03-23 | Full content gap analysis done — see research/content-gap-analysis.md | imagine.io has strong content but wrong structure; physicl.ai earns trust before explaining |
| 2026-03-23 | Flat outputs structure — `outputs/page-vN.html` | No nested folders; cleaner file management |
| 2026-03-23 | design-reference.md created at research/design-reference.md | Living doc for all reference site analysis; not tied to one site |
| 2026-03-23 | Deep visual analysis of physicl.ai done (7 screenshots) | 5 priority changes identified for v3: social proof above headline, vertical pipeline, layered code+asset section, image-first use case cards, asymmetric CTA |
| 2026-03-24 | Icon library hierarchy added to Prism Design System globally | Material Symbols Outlined = default; Phosphor Icons = fallback; Lucide Icons = second fallback. Never mix libraries without clear reason. Updated `~/.claude/prism-design-system.md`. |
| 2026-03-24 | Real product images from `github.com/vipinmeena1468/library-assets` replace all placeholders in v3 | 38 placeholder divs replaced across marquee cards, use-case cards, validation cards, and CTA grid. Images pulled via `raw.githubusercontent.com` — no local files needed. |
| 2026-03-25 | Image CDN switched from raw.githubusercontent.com → jsDelivr CDN in v3 | Faster delivery via edge CDN. Zero changes to the library-assets repo. URL pattern: `cdn.jsdelivr.net/gh/vipinmeena1468/library-assets@main/...` |
| 2026-03-25 | PM reference site fetched and full content audit done | PM site: `imagine-site-kappa.vercel.app`. Major differences found in nav, hero, pain points, section structure, and missing sections (Product Graph, Deliverables, Ecosystem, GTC). |
| 2026-03-25 | Homepage v4 started — v3 duplicated, content aligned with PM site | v4 = v3 visual design + PM content. New sections added: What You Get (9 deliverables), Ecosystem (4 partners), GTC event section. See v4 section map below. |
| 2026-03-25 | All 5 pending v4 UI fixes completed | id="platform" moved to section; .btn-lg height reduced; trust copy updated to PM framing; use case panels updated to PM copy; section label design resolved. |
| 2026-03-25 | Section label (.pill) design: neutral grey rounded box | Went through Options B (monospace bracket), D (overline), user's own direction. Settled on: `background: rgba(0,0,0,0.06); color: var(--text-muted); border-radius: 6px`. No pill/capsule shape anywhere on the page. |
| 2026-03-25 | Full UI audit done — accent color overuse identified and resolved | Papaya/accent was used in 9+ unrelated elements. Now restricted to: (1) primary CTA buttons only, (2) one `<em>` phrase in the hero h1. All icons, labels, step numbers, dots, and decorative elements switched to muted/neutral. |
| 2026-03-25 | Hero h1 updated: two-liner with accent on last phrase | Old: `Physical AI.` (accent, isolated). New: `Structured data / for Physical AI.` — "Physical AI." is the only accent-colored text. |
| 2026-03-25 | Badge shapes unified — no border-radius: 100px anywhere | All capsule/pill shapes replaced with rectangular badges (4–6px radius). Affected: tier status tags (Ready Now / Near-Ready / Roadmap), Verified badges on all image cards (marquee, validation, CTA grid), GTC "Live Event" badge. |
| 2026-03-25 | Hero stats bar: SOC 2 replaced with 150+ Metadata Attributes | SOC 2 is a compliance badge, not a number — doesn't belong in a numeric proof strip. Replaced with a product-specific differentiator. |
| 2026-03-25 | Orange `<em>` accent added to every section h2 headline | All section h2s now have one orange word/phrase via `h2 em { color: var(--accent) }`. Applied to both `homepage-v4.html` and `index.html`. See Design Rule #8 below. |
| 2026-03-25 | Specific word-level orange highlights refined per visual review | Validation: "asset." + "variant." orange; Tiers: "Perception", "Navigation", "Manipulation" each individually orange; Ecosystem: "run the simulation." orange. |
| 2026-03-25 | Auto-save Stop hook added to `.claude/settings.json` | Runs `git add -A && git commit && git push` on every Claude session end — ensures team always sees latest WIP even if tokens run out mid-session. |
| 2026-03-25 | Homepage v5 started — hero section fully refactored | v4 duplicated to v5. Hero rebuilt into 3-layer structure: (1) headline/CTA, (2) dark code editor (Isaac Sim Python, file tabs, line numbers), (3) two animated asset strip rows. Stats moved out of hero into standalone bar below. |
| 2026-03-25 | CSS/HTML separated from v5 onwards | `outputs/homepage-vN.html` + `css/homepage-vN.css` (root level). No inline `<style>` blocks from v5 onwards. Rule documented in CLAUDE.md and SUMMARY.md. |
| 2026-03-25 | Homepage v6 created — hero overhaul + polish pass | v5 base. Hero changes: white bg (no dot pattern), dark code editor replaced with light-theme Scene Builder UI (sidebar + floor plan canvas + properties bar), proof badge + old h1 removed, subtitle promoted to h1 with "simulation-ready" in orange, body copy kept. Strips + pain marquee removed. Navbar: border removed, glassmorphic (`rgba(255,255,255,0.65)` + `blur(24px) saturate(1.8)`), dark logo. Stats bar sits directly below editor. Partners logo strip: 5 real PNG logos from `partners-logos/` folder, greyscale/muted treatment, `116px` vertical padding. |
| 2026-03-25 | v6 logo strip rebuilt from scratch | Old `.proof` class completely removed from HTML + CSS. New `.logo-strip` namespace. `padding: 48px 0`, thin top/bottom borders, `height: 22px` logos, `grayscale(100%) opacity: 0.5` default, hover restores color. Label: "Integrates with your pipeline". Lives as standalone section between stats bar and asset showcase. |
| 2026-03-25 | v6 asset card system refactored | Old `.asset-card__sim`, `.asset-card__verified`, `.asset-card__verified-dot` removed. New: `aspect-ratio: 4/3`, absolute-positioned `__img` layer, full-bleed gradient overlay (`__overlay` → `__bottom`), unified `.asset-badge` pill (`.asset-badge--left` / `--right`, `backdrop-filter: blur(6px)`). Hover: card lifts `translateY(-4px)`, image scales `1.05`. |
| 2026-03-25 | v6 asset cards — Apparel images replaced with Kitchen + Bath | All 4 Apparel image references removed. Replaced with: `Kitchen/Dutch Oven_Image 1.jpg` ("Kitchen Environments"), `Bath/Walnut Vanity_Image 1.jpg` ("Bathroom Spaces"), `Kitchen/Kitchen Faucet_Image 1.jpg` ("Kitchen & Bath Fixtures"), `Bath/Bathtub_Image 1.jpg` ("Spa & Wellness"). Categories now: Furniture, Lighting, Kitchen, Bath only. |
| 2026-03-25 | v6 bug fix — background:url() → background-image:url() | Inline `background:` shorthand was overriding `background-size: cover` and `background-position: center` from CSS class, causing images to not fill card frames. Fixed all 45 occurrences to use `background-image:` instead. |
| 2026-03-25 | index.html updated to v6 — now live on Vercel | `cp outputs/homepage-v6.html index.html` + pushed to main. Vercel auto-deployed. CSS cache at `?v=7`. |
| 2026-03-26 | Homepage v7 created — section reorder | v6 duplicated to `outputs/homepage-v7.html` + `css/homepage-v7.css`. One change: "Asset Library" (`.showcase`) section moved from above the Proof section to directly after the Deliverables section. No internal changes to either section. |
| 2026-03-26 | Figma design file added to project | Imagine.io x Physical AI — fileKey: `1aL836P4R3p09gOwE5TVQz`. This is the primary Figma file designers will use for this project. |
| 2026-03-30 | v7 Pipeline / "How It Works" rebuilt as sticky-scroll | Replaced simple stacked rows with physicl.ai-style sticky-scroll pattern. Architecture: tall `.pipeline-scroll__track` (200vh) + `position: sticky; top: 0; height: 100vh` inner. Left panel: 3 `.ps-step` items (step number, title, description — no icons); opacity fades for inactive steps, description expands for active. Right panel: 3 `.ps-visual` items absolutely positioned inside a warm container stage (`background: #ede9e3; border-radius: 16px; padding: 28px`); only `.ps-visual--active` visible (opacity 1 + translateY(-50%)); inactive offset by `calc(-50% + 18px)` for smooth enter-from-below animation. JS activator: scroll progress maps to step index via `scrolled / (trackHeight - viewportHeight)`. CSS transition: `cubic-bezier(0.25, 0.46, 0.45, 0.94)` at 0.65s. Images pulled from jsDelivr CDN. Visual 3 uses `Lighting/Kessler Table Lamp_Image 3.jpg`. CSS cache bumped to `?v=6`. |
| 2026-03-30 | "Built for your team" Use Cases section removed from v7 | Entire `.usecase` section (HTML + CSS) deleted. Sections above and below adjusted. |
| 2026-03-30 | PM site comparison done — one missing section identified | Fetched `imagine-site-kappa.vercel.app`. v7 is aligned with PM site except one gap: PM site has a **Moat section** between Product Graph and Pipeline ("This model comes from years of production use in configurable product and scene generation. Built from production product infrastructure, not hand-authored scenes."). v7 also has Asset Showcase marquee and Validation section which PM site does not have. Decision on adding Moat section is pending user input. |
| 2026-03-30 | v7 promoted to index.html — now live on Vercel | `outputs/homepage-v7.html` copied to `index.html` (root) with all `../` path prefixes stripped. Committed and pushed to `main`. Vercel auto-deployed. v7 is now the live version. |
| 2026-03-30 | Project folder cleaned up and reorganized | `outputs/v1–v6` + `css/v5–v6` moved to `archive/`. `partners-logos/` moved to `assets/partners-logos/`. `prism-design-system.md` removed from project root (duplicate of global `~/.claude/`). All `?v=N` cache busting removed from `homepage-v7.html` and `index.html`. References updated. |
| 2026-03-31 | v8 CSS fully audited for PDS compliance | `:root` aliases updated: `--accent` → `var(--papaya-500)`, `--accent-dark` → `var(--papaya-600)`, `--bg` → `var(--white)`. All non-PDS values documented as exceptions with comments. Hardcoded `#fff`/`#ffffff` replaced with `var(--bg)` or `var(--white)`. `#141414` → `var(--dark)`. Spacing values throughout replaced with PDS tokens (`--s-200` through `--s-1400`) where exact matches exist. Values with no PDS token (80px, 100px, 6px/12px radius) kept as documented exceptions. |
| 2026-03-31 | v8 copy rewritten across all sections | Goal: clear for both marketing and technical audiences. Key changes: (1) "What is a product graph?" → "The structured model behind every environment we generate." (2) Pipeline h2: "The system that produced what you just saw." → "From structured product data to training-ready environments." (3) Step descriptions trimmed and clarified. (4) Hero body shortened. (5) Problem card bodies trimmed. (6) Validation body tightened. (7) Tiers sub rewritten to match h2 rhythm. (8) Trust body simplified — stats not repeated since they appear in stat grid. (9) Deliverables sub updated with specific tool names (Isaac Sim, MuJoCo). |
| 2026-03-31 | v9 created — Blueprint theme implementation (in progress) | New visual language: engineering schematic/blueprint aesthetic. (1) CSS Foundation: `--bp-mark`, `--bp-mark-dark`, `--bp-dash`, `--bp-arm` tokens added; `.bp-frame` crosshair corner system (JS injects 4 `.bp-corner` spans per `.bp-frame` element); scroll-reveal system (`.reveal`, `.reveal--left/right`, stagger variants `--1` through `--6`) via IntersectionObserver. (2) Navbar: sharp 4px radius (vs 8px pill), blueprint border on scrolled state. Dark logo (Horizontal.svg) for light bg. (3) Hero: subtle crosshair grid background via SVG data URI; editor frame uses `var(--bp-mark)` border + 4px radius + `bp-frame` corners. (4) Stats bar + Logo strip: `var(--bp-mark)` borders; logos greyscale 45% opacity + hover restores color. (5) All cards redesigned: problem, deliverables, ecosystem, validation, pipeline (ps-card), asset, CTA image cards — all now 4px radius, `var(--bp-mark)` border. (6) Dark sections (code-layer, GTC): crosshair grid via SVG data URI on dark bg. (7) Pill badges: transparent bg, thin 1px `var(--bp-mark)` border. (8) All section headings, content blocks, cards tagged with `reveal` / `reveal--left` / `reveal--right` / stagger classes. 43 reveal instances + 14 bp-frame instances across the HTML. |
| 2026-03-31 | v10: stats bar removed; mission section restructured | Stats bar (standalone section after hero) removed. Mission section (`#proof`) rebuilt into a two-column layout: left = h2 + body + 4 feature list items; right = full product image (`Bath/Bathtub_Image 1.jpg`). Stats row (6+, 1M+, 25K+, 10,000×, 150+) moved inside the mission section below the two-column grid, with orange accent numbers. Feature list icons switched from accent to `var(--text-muted)`. |
| 2026-03-31 | v10: adaptive dark/light navigation | Navbar now detects when it overlaps a dark section (`[data-theme="dark"]`) and switches to dark mode: white-tinted links, dark glass pill (`rgba(14,14,14,0.82)` + `blur(20px)`), white border. Logo swaps between `Horizontal Dark.png` (default) and `Horizontal Light.png` (on dark). Both `.code-layer#platform` and `.gtc#gtc` tagged with `data-theme="dark"`. Detection uses scroll-based `getBoundingClientRect` check — smooth, no flash. |
| 2026-03-31 | v10 promoted to index.html — now live on Vercel | `outputs/homepage-v10.html` copied to `index.html` with `../` path prefixes stripped. Committed and pushed to `main`. **v10 is now the live version.** |
| 2026-04-02 | Image repo migrated from `vipinmeena1468/library-assets` → `imaginevipin/imagine-assets-library` | New repo has a different structure: `01 Silo/[Category]/[Product]/[file].webp` and `02 Lifestyle/[Category]/[Product]/[file].webp`. All `.jpg`/`.png` files replaced with `.webp`. Applied across v7–v10 + index.html. Apparel category no longer exists — substituted with `02 Lifestyle/Textiles/`. Coffee Table and Console have no equivalent — substituted with Melrose Upholstered Sectional and Lucinda Nightstand respectively. `Chair Silo frt.png` → Aspen Side Chair image 1. |

---

## Build Log

| Date | Output | Path | Notes |
|------|--------|------|-------|
| 2026-03-23 | Homepage v1 — static | `outputs/homepage-v1.html` | All 14 sections, real copy, Prism tokens, black placeholders for images. No animations. |
| 2026-03-23 | Homepage v2 — full redesign | `outputs/homepage-v2.html` | Light theme only, infinite marquee carousels, massive breathing space, papaya-tinted stat section, editorial typography, premium card design. |
| 2026-03-23 | Homepage v3 — physicl.ai pattern overhaul | `outputs/homepage-v3.html` | 5 priority changes: social proof above headline, vertical pipeline rows w/ progressive opacity, code demo layered over dark asset grid, image-first use case cards, asymmetric CTA. Also: bordered pill badges, periods on headlines, Verified badges on all image cards, flush ruled tiers, Material Symbols icons. Papaya primary CTAs. |
| 2026-03-24 | Homepage v3 — real images + CDN | `outputs/homepage-v3.html` | All 38 placeholder divs replaced with real product imagery. CDN switched to jsDelivr for faster loading. |
| 2026-03-25 | Homepage v4 — complete | `outputs/homepage-v4.html` | Content aligned with PM site + full UI polish pass. See section map and design decisions below. |
| 2026-03-25 | Homepage v5 — hero refactor (WIP) | `outputs/homepage-v5.html` + `css/homepage-v5.css` | 3-layer hero: headline → dark code editor → animated asset strips. Stats bar below hero. First version with external CSS file. |
| 2026-03-25 | Homepage v6 — complete, live on Vercel | `outputs/homepage-v6.html` + `css/homepage-v6.css` (CSS cache `?v=7`) | White hero bg, light Scene Builder UI editor (460px tall), h1 = "Structured product data for simulation-ready world generation." (orange on "simulation-ready"), glassmorphic navbar, `.logo-strip` partner section, refactored asset cards (`aspect-ratio: 4/3`, full-bleed image + gradient overlay, `.asset-badge` pills, Furniture/Lighting/Kitchen/Bath images). Copied to `index.html` and deployed. |
| 2026-03-26 | Homepage v7 — WIP | `outputs/homepage-v7.html` + `css/homepage-v7.css` (CSS cache `?v=1`) | v6 base. Section reorder: Asset Library now sits after Deliverables. Active version being edited. |
| 2026-03-30 | Homepage v7 — complete, live on Vercel | `outputs/homepage-v7.html` + `css/homepage-v7.css` | Major changes from v6: (1) Pipeline rebuilt as sticky-scroll (physicl.ai reference) — 200vh track, sticky inner, 3 steps with animated descriptions, 3 absolutely-positioned visuals inside warm container stage; (2) "Built for your team" use cases section removed; (3) copied to `index.html` and deployed to Vercel. **v7 is now locked — do not edit.** |
| 2026-03-30 | Homepage v8 — setup | `outputs/homepage-v8.html` + `css/homepage-v8.css` | Duplicated from v7. Active working version. |
| 2026-03-31 | Homepage v8 — CSS PDS audit + full copy rewrite | `outputs/homepage-v8.html` + `css/homepage-v8.css` | CSS: all tokens now reference PDS or documented as exceptions. HTML: all section copy rewritten for dual marketing/technical audience. |
| 2026-03-31 | Homepage v9 — blueprint theme WIP | `outputs/homepage-v9.html` + `css/homepage-v9.css` | Blueprint/engineering schematic theme experiment. Did not look good — parked. Not to be promoted to index.html. |
| 2026-03-31 | Homepage v10 — setup, active working version | `outputs/homepage-v10.html` + `css/homepage-v10.css` | Duplicated from v8 (clean base). Logo updated to PNG (`Horizontal Light.png`). Blueprint theme to be applied here going forward. |
| 2026-03-31 | Homepage v10 — mission section + dark nav | `outputs/homepage-v10.html` + `css/homepage-v10.css` | Stats bar removed. Mission section rebuilt: two-column (copy left, image right), stats row below with orange numbers. Adaptive navbar: detects dark sections via `data-theme="dark"`, switches to dark glass + white links + white logo. Promoted to `index.html` and deployed to Vercel. **v10 is now live.** |

---

## Homepage v4 — Section Map

| # | Section | Status | Notes |
|---|---------|--------|-------|
| 1 | Navbar | ✅ Done | Links: Proof / Platform / Tiers / GTC. CTA: "Book a Technical Discussion" |
| 2 | Hero | ✅ Done | H1: "Structured data / for Physical AI." — accent on "Physical AI." only. Stats: 6+, 1M+, 25K+, 10K×, 150+. Proof strip removed from above headline. |
| 3 | Pain Marquee | ✅ Done | PM's specific pain points: "40h rigging per kitchen", "ML engineers debugging UV maps", etc. Separator dots now muted (not accent). |
| 4 | Logo Strip | ✅ Done | Unchanged from v3 |
| 5 | Proof Section | ✅ Done | "Built as structured data. Exported as simulation-ready worlds." id="proof". 4 capability items. Icons muted. |
| 6 | Asset Showcase Marquees | ✅ Done | 2 rows of scrolling image cards. Verified badges now rectangular (4px radius). |
| 7 | Product Graph (dark) | ✅ Done | id="platform" on `<section>` element (not h2). Scene graph JSON code block. 4 component features with muted icons. |
| 8 | How It Works | ✅ Done | PM's 3 steps: Tagged Scene Graph / Parameter Variation / Perception Training. Step numbers muted. |
| 9 | What You Get | ✅ Done | 9 deliverables grid on warm bg: OpenUSD, Labels, Collision, Joints, Frames, JSON, Lighting, Variations, Cameras. Icons and format tags neutral. |
| 10 | Why Different (Stats) | ✅ Done | "Not procedural. Not AI-synthesized." 4 stats. Stat `em` suffixes now dark (not accent). |
| 11 | Use Cases | ✅ Done | Image cards + detail panels. Robotics panel: Tagged Scene Graph / Parameter Variation / Perception Training language. Foundation Models panel: 150+ metadata attributes, product graph differentiator. Check icons muted. |
| 12 | Validation Showcase | ✅ Done | Sticky left + scrolling right cards. Verified badges rectangular. |
| 13 | Application Tiers | ✅ Done | id="tiers". Perception (Ready Now) / Navigation (Near-Ready) / Manipulation (Roadmap). Status badges rectangular (6px radius), colors retained (green/yellow). Feature icons muted. |
| 14 | Ecosystem | ✅ Done | 4 partner cards: NVIDIA Omniverse, Isaac Sim, OpenUSD/SimReady, MuJoCo |
| 15 | Trust / Why This Is Different | ✅ Done | Pill: "Why This Is Different". H2: "Not procedural. Not AI-synthesized. Structured from the source." Stats: 150+ metadata attributes, 1M+ outputs/month, 25K+ products, 5K+ environments. |
| 16 | GTC | ✅ Done | Dark section. id="gtc". "Live Event" badge rectangular + neutral. GTC glow and detail icons neutral (not accent). |
| 17 | Final CTA | ✅ Done | "Bring your stack. We'll show the pipeline." Verified badges rectangular. |
| 18 | Footer | ✅ Done | PM tagline: "Structured World Infrastructure for Physical AI". Contact: San Francisco · preet@imagine.io |

---

## Design Rules Established for This Project

These were discovered and locked in during v4 polish — apply in all future work:

1. **Accent color (papaya)** — used in exactly 3 places: primary CTA buttons, one `<em>` phrase in the hero h1, and one `<em>` word/phrase in each section h2 headline.
2. **Icons** — always `var(--text-muted)` on light sections, `rgba(255,255,255,0.35)` on dark sections. Never accent-colored.
3. **Section label badges (`.pill`)** — `background: rgba(0,0,0,0.06); color: var(--text-muted); border-radius: 6px`. On dark sections: `background: rgba(255,255,255,0.08); color: rgba(255,255,255,0.45)`.
4. **Badge shapes** — no `border-radius: 100px` anywhere. All badges/tags: 4–6px radius. Capsule/pill shape is banned.
5. **Stat numbers** — no accent coloring on `em` suffixes (+, ×, etc.). Use `var(--text-head)`.
6. **Step/sequence numbers** — muted, not accent.
7. **Button sizing** — `.btn-lg`: `padding: 9px 22px; font-size: 14px` (matches nav button proportions).
8. **Section h2 orange highlights** — every section h2 has exactly one `<em>`-wrapped word or phrase in orange. Rule: `h2 em { font-style: normal; color: var(--accent); }` — a single global CSS rule handles all sections. Each highlight is chosen to emphasise the most specific/differentiating phrase in the headline, not the whole sentence.
9. **No CSS cache busting** — never append `?v=N` query strings to CSS `<link>` hrefs. Each version pair (`homepage-vN.html` + `homepage-vN.css`) is the single source of truth. For significant changes, move to the next version (e.g. v7 → v8), not a cache bump.
10. **Prism Design System is mandatory** — all colors, typography, spacing, and borders must use PDS tokens from `tokens.css`. Never hardcode hex values, px sizes, or arbitrary spacing. Exception only when a UI component requires something genuinely not covered by PDS — document the exception explicitly in SUMMARY.md.
11. **Model usage** — Haiku for quick answers/small edits; Sonnet for most work (UI, coding, iteration); Opus for deep research, complex tasks, advanced coding. Always match model to task to manage token cost.

---

## GitHub Repository

- **Repo:** `github.com/imaginevipin/Imagineio-x-Physical-AI` — **private**
- **Auth:** GitHub CLI (`gh`) authenticated as `imaginevipin` (vipin.meena@imagine.io)
- **Git identity:** `git config --global user.name "imaginevipin"` / `user.email "vipin.meena@imagine.io"`
- **Remote:** `https://github.com/imaginevipin/Imagineio-x-Physical-AI.git`
- **Branch:** `main`
- **What's in the repo:**
  - `outputs/` — current active version: `homepage-v10.html`
  - `archive/outputs/` — v1–v6 HTML (history only)
  - `archive/css/` — v5–v6 CSS (history only)
  - `css/` — current: `homepage-v10.css`
  - `assets/fonts/` — PP Neue Montreal (6 OTF weights)
  - `assets/logos/` — all imagine.io SVG variants
  - `assets/partners-logos/` — 5 partner PNGs (Logo-1 to Logo-5)
  - `research/` — content gap analysis, design reference
  - `tokens.css`, `CLAUDE.md`, `PLAN.md`, `SUMMARY.md`
  - `.claude/settings.json` — Stop hook: auto git commit + push on session end

**To push updates:**
```bash
git add .
git commit -m "your message"
git push
```

---

## Vercel Deployment

- **Goal:** deploy final version as a live URL (Vercel)
- **Status:** Live — `index.html` = homepage-v10, deployed via Vercel auto-deploy on push to `main`
- **Setup (one-time):**
  1. Go to vercel.com → Add New → Project → Import `imaginevipin/Imagineio-x-Physical-AI`
  2. Framework: `Other` — leave all settings as default (root `/`, no build command)
  3. Hit Deploy — every future push to `main` auto-deploys
- **Note:** Vercel free (Hobby) plan supports private repos via GitHub OAuth — no paid plan needed

### index.html Workflow

- `index.html` lives at the **project root** — this is the live version Vercel serves
- It is always a copy of the latest approved output (currently: **homepage-v10**)
- `outputs/` folder is untouched version history — never delete or overwrite files there
- **To update the live site:** copy the new approved version over `index.html`, strip `../` path prefixes (since `index.html` is at root, not in `outputs/`), then push
  ```bash
  sed 's|"\.\./|"|g' outputs/homepage-v10.html > index.html
  git add index.html && git commit -m "vN promoted to index.html — now live on Vercel" && git push
  ```

---

## Image Source

All product images are served from the `imagine-assets-library` GitHub repo via jsDelivr CDN:
- **Repo:** `github.com/imaginevipin/imagine-assets-library`
- **Structure:** Two top-level folders — `01 Silo/` (white-bg product shots) and `02 Lifestyle/` (styled scene shots). Each contains category subfolders → product subfolders → `.webp` files.
- **CDN pattern:** `https://cdn.jsdelivr.net/gh/imaginevipin/imagine-assets-library@main/01%20Silo/[Category]/[Product]/[Product]_image%20N.webp`
- **Categories used:** Furniture, Lighting, Kitchen, Bath, Case Goods (Silo); Furniture, Textiles, Case Goods (Lifestyle)
- Images can be used freely across our HTML files — just reference via CDN URL.

---

## Known Issues / Pending Items

- `homepage-v10` is the **active working version** and is **live on Vercel** via `index.html`. ✅
- `homepage-v7` is locked — kept in `outputs/` as version history only.
- `homepage-v9` is parked — blueprint theme experiment that didn't look good. Not to be used.
- `com.apple.provenance` extended attribute appears on all files in the `css/` folder (macOS behavior) — does NOT block writes; file is writable by owner.
- **Pending decision:** Add a Moat section? PM site has one between Product Graph and Pipeline. Decision deferred.
- **CSS compliance:** `homepage-v10.css` is PDS-compliant. Documented exceptions: `--bg-warm`, `--bg-subtle`, `--border`, `--text-head`, `--text-body`, `--text-muted`, `--radius-sm/md/lg`, `--section-y`, plus spacing above 72px and decorative UI colors (macOS window dots, code syntax colors, status badges).
- **Logos:** PNG files (`Horizontal Dark.png`, `Horizontal Light.png`, `Vertical Dark.png`, `Vertical Light.png`, `Logo Mark.png`) in `assets/logos/`. Old SVGs kept alongside. v10 uses dual logo system: `Horizontal Dark.png` default; `Horizontal Light.png` on dark sections.

---

## Next Steps

1. **v10 is live** — promoted to `index.html` and deployed. Active working version for continued iteration.
2. **v10 section order (current):** Navbar → Hero → Logo Strip → Mission (proof + stats) → Problem → Code Layer (dark) → Pipeline → Deliverables → Asset Showcase → Validation → Tiers → Why Different → Ecosystem → GTC (dark) → Final CTA → Footer.
3. **Adaptive dark nav** — implemented. Detects `.code-layer` and `.gtc` dark sections. Add `data-theme="dark"` to any new dark section to automatically inherit the behaviour.
4. **Moat section** — deferred. Decide before next major version bump.
5. **Continued v10 polish** — further section-level UI refinements as needed before declaring final.
6. **Inner pages:** `robotics-v1.html`, `foundation-models-v1.html`, `company-v1.html` — to start after v10 is declared final.
