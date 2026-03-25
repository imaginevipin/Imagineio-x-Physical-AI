# Project Summary — Imagineio Physical AI

> **For Claude:** Read this file at the start of every conversation to restore full project context. Update it after every significant decision, build, or iteration — especially before the user clears the chat.

---

## Project Identity

- **Client / Brand:** imagine.io
- **Project:** Physical AI (name TBD)
- **Design System:** Prism — tokens in `tokens.css`, fonts in `assets/fonts/`, logos in `assets/logos/`

---

## Model Usage

| Task Type | Model | When to Use |
|-----------|-------|-------------|
| Quick answers, small edits | Haiku (`claude-haiku-4-5-20251001`) | Fast lookups, minor copy changes, simple questions |
| Most work | Sonnet (`claude-sonnet-4-6`) | UI builds, standard coding, iteration |
| Deep research, complex tasks | Opus (`claude-opus-4-6`) | Architecture decisions, advanced coding, research |

---

## Outputs Structure

All deliverables go in `outputs/` as flat files — naming convention: `[page-name]-v[N].html` (e.g. `homepage-v2.html`, `robotics-v1.html`). Never overwrite — always create a new version file.

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

---

## Build Log

| Date | Output | Path | Notes |
|------|--------|------|-------|
| 2026-03-23 | Homepage v1 — static | `outputs/homepage-v1.html` | All 14 sections, real copy, Prism tokens, black placeholders for images. No animations. |
| 2026-03-23 | Homepage v2 — full redesign | `outputs/homepage-v2.html` | Light theme only, infinite marquee carousels, massive breathing space, papaya-tinted stat section, editorial typography, premium card design. |
| 2026-03-23 | Homepage v3 — physicl.ai pattern overhaul | `outputs/homepage-v3.html` | 5 priority changes: social proof above headline, vertical pipeline rows w/ progressive opacity, code demo layered over dark asset grid, image-first use case cards, asymmetric CTA. Also: bordered pill badges, periods on headlines, Verified badges on all image cards, flush ruled tiers, Material Symbols icons. Papaya primary CTAs. |
| 2026-03-24 | Homepage v3 — real images + CDN | `outputs/homepage-v3.html` | All 38 placeholder divs replaced with real product imagery. CDN switched to jsDelivr for faster loading. |
| 2026-03-25 | Homepage v4 — complete | `outputs/homepage-v4.html` | Content aligned with PM site + full UI polish pass. See section map and design decisions below. |

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

1. **Accent color (papaya)** — used in exactly 2 places only: primary CTA buttons, and one `<em>` phrase in the hero h1. Nothing else.
2. **Icons** — always `var(--text-muted)` on light sections, `rgba(255,255,255,0.35)` on dark sections. Never accent-colored.
3. **Section label badges (`.pill`)** — `background: rgba(0,0,0,0.06); color: var(--text-muted); border-radius: 6px`. On dark sections: `background: rgba(255,255,255,0.08); color: rgba(255,255,255,0.45)`.
4. **Badge shapes** — no `border-radius: 100px` anywhere. All badges/tags: 4–6px radius. Capsule/pill shape is banned.
5. **Stat numbers** — no accent coloring on `em` suffixes (+, ×, etc.). Use `var(--text-head)`.
6. **Step/sequence numbers** — muted, not accent.
7. **Button sizing** — `.btn-lg`: `padding: 9px 22px; font-size: 14px` (matches nav button proportions).

---

## Known Issues / Pending Items

None outstanding. v4 is complete and reviewed.

---

## Image Source

All product images are served from the `library-assets` GitHub repo via jsDelivr CDN:
- **Repo:** `github.com/vipinmeena1468/library-assets` — **DO NOT MODIFY this repo.** Other products use it.
- **CDN pattern:** `https://cdn.jsdelivr.net/gh/vipinmeena1468/library-assets@main/[Category]/[filename]`
- **Categories used:** Furniture, Lighting, Apparel
- Images can be used freely across our HTML files — just reference via CDN URL.

---

## Next Steps

1. Review completed v4 with user — get final approval
2. After homepage approved: build `robotics-v1.html`, `foundation-models-v1.html`, `company-v1.html`
