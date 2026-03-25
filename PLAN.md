# Project Plan — imagine.io Physical AI Website
**Created:** 2026-03-23 | **Last updated:** 2026-03-24 | **Model used for research:** Opus

---

## 1. Research Summary

### 1A. What physicl.ai Does (Reference Site)

Physicl.ai is a **training data infrastructure company for Physical AI**. They generate, normalize, validate, and deliver physics-accurate 3D assets and simulation environments for robotics and foundation model teams. Their key claim: *Physical AI is data-limited, not model-limited. Physicl exists to fix that.*

### 1B. What imagine.io Does (Our Site)

imagine.io offers data that powers Physical AI and robotics training. The positioning is identical in spirit — we have the data assets, scale, and quality pipeline that AI/robotics teams need. The website needs to communicate this clearly, credibly, and visually compellingly.

---

## 2. UX Research Findings

### 2A. Information Architecture (How the reference site thinks)

| Layer | Purpose | What it achieves |
|-------|---------|-----------------|
| **Hero** | Single-sentence positioning + dual CTA | Tells you exactly what they do in 5 seconds |
| **Social proof (immediate)** | Logos + "187+ teams" right after hero | Prevents "who are you?" skepticism before it forms |
| **Asset showcase carousel** | Infinite scroll of 3D content types | Proves scale and breadth before explaining it |
| **Mission + code demo** | "We build the data..." + Python API | Shifts from what to how — builds technical credibility |
| **5-step pipeline** | Ingest → Normalize → Augment → Validate → Deploy | Answers "how does it work?" with process clarity |
| **Problem stats** | 98% sim-ready, speed claims, physics tagging | Numbers that differentiate from alternatives |
| **Use case split** | Robotics vs. Foundation Models | Segments audience — each visitor sees their path |
| **Validation showcase** | Asset variants with verified counts | Proves quality, not just quantity |
| **Community trust** | 10k validators, QC rate, RLHF, Getty | Third-party credibility layer |
| **Final CTA** | Enterprise names + dual buttons | Closes with authority, creates scarcity |

### 2B. Narrative Arc (The Story Structure)

```
Act I — Hook & Proof
  → "Here's what we do" (hero)
  → "Here's who trusts us" (social proof)
  → "Here's how much we have" (asset showcase)

Act II — Technical Depth
  → "Here's our mission" (mission statement)
  → "Here's how it works" (code demo + pipeline)
  → "Here's why you need this" (problem stats)

Act III — Audience Fit
  → "Here's what we offer robotics teams"
  → "Here's what we offer foundation model teams"

Act IV — Proof of Quality
  → "Here's our validation process" (asset variants)
  → "Here's our community" (validators + partnership)

Act V — Conversion
  → "Join these teams" (enterprise logos + CTA)
```

### 2C. UX Patterns That Work (to replicate)

1. **Dual CTA model** — Primary (beta/waitlist) + Secondary (talk to sales). Never a single button. Creates two entry points for different stages of the buying journey.
2. **Immediate logos** — Social proof logos appear within the first scroll. Reduces bounce for high-intent visitors who validate credibility before reading.
3. **Asset abundance first, explanation second** — Carousels showing hundreds of assets before any methodology text. "Show, then tell."
4. **Numbered pipeline steps** — 01–05 framing turns a complex process into a digestible journey. Reduces cognitive load.
5. **Use case segmentation** — Splitting the page for Robotics vs. Foundation Models lets each audience self-identify and feel the product is built for them.
6. **Specificity in stats** — "98% sim-ready out-of-box", "100k assets/month", "3 RLHF levels" — not vague claims, specific numbers that signal real operations.
7. **Code demo** — A working API example builds instant developer credibility. Says "this is real and usable" without a word of prose.
8. **Verified counts on assets** — "3,831+ bedroom scenes" on each tile. Makes the library feel searchable and concrete, not abstract.
9. **Marquee / infinite scroll** — Visual momentum without requiring user action. Suggests constant production, constant supply.

### 2D. UX Gaps / What We Can Improve

1. **Clearer value proposition hierarchy** — Physicl's hero copy ("high-fidelity 3D scenes and physics-grounded assets") is slightly jargon-heavy up front. We can lead with the business outcome first ("Train faster. Deploy with confidence.") then layer in the technical specifics.
2. **Faster segmentation** — Physicl waits until mid-page to split Robotics vs. Foundation Models. We could surface this choice higher (e.g., right below the hero) so visitors find their path faster.
3. **Better mobile scroll story** — Physicl's pinned-tab desktop experience collapses into auto-playing carousels on mobile, which loses some impact. We should design both experiences intentionally from the start.

---

## 3. UI Research Findings

### 3A. Visual Language

| Element | Physicl's Approach | Our Adaptation (Prism) |
|---------|-------------------|----------------------|
| **Background** | Dark warm-brown (`#171412`) for most sections | Use `--dark: #141414` for dark sections |
| **Primary brand color** | Blue accent `#4d65ff` | Use `--papaya-500: #ec4e0b` (our primary) |
| **Light sections** | Near-white `#F5F5F4` | Use `--surface-page: #ffffff` and `--surface-page-secondary: #f6f6f6` |
| **Card backgrounds** | Warm tan/grey tones | Use `--grey-50` through `--grey-100` |
| **Accent/highlight** | Warm tan `#C4A882` on active tabs | Use `--papaya-300` or `--papaya-400` for active states |
| **Text on dark** | Near-white `#F5F5F4` | Use `--text-on-color-heading: #ffffff` |
| **Text on light** | Near-black `#101223` | Use `--text-default-heading: #1a1a1a` |

### 3B. Typography Mapping

| Usage | Physicl | Our Approach (Prism) |
|-------|---------|---------------------|
| Hero H1 | Large, display weight, bold | H1 — 60px, Regular (400), -2px tracking |
| Section H2 | Medium-large, lighter weight | H2 — 48px, Regular (400), -2px tracking |
| H3 subsections | Semibold | H3 — 40px, SemiBold (600), -1px tracking |
| Body copy | 16–20px, clean | body / body-lg tokens |
| Stats/numbers | Large, display | H1 or H2, SemiBold |
| Labels/badges | Small, uppercase tracking | small / caption tokens |
| Code | Monospace | External monospace (e.g., `IBM Plex Mono`) |

### 3C. Component Inventory (to build)

| Component | Description | Priority |
|-----------|-------------|----------|
| **Navbar** | Logo left, nav center, CTA right. Scrolls to dark/light based on section bg | P1 |
| **Hero section** | Full-width, centered text, H1 + subtitle + dual CTA | P1 |
| **Marquee (horizontal)** | Infinite-scroll asset tiles with image + label + count | P1 |
| **Marquee (vertical)** | Infinite-scroll asset cards, two columns, opposite directions | P1 |
| **Logo strip** | Client logos in a row, muted opacity, full-width | P1 |
| **Stat blocks** | Large number + label + optional supporting copy | P1 |
| **Pipeline steps** | Numbered 01–05 horizontal (desktop) / stacked (mobile) | P1 |
| **Code block** | Syntax-highlighted, typing animation | P2 |
| **Asset card** | Image + category badge + verified count | P1 |
| **Tab switcher** | Active tab highlights, progress bar or scroll-driven | P2 |
| **Use case split** | Two-column layout, each side for a different audience | P1 |
| **Team/community stats** | Icon + large number + label in grid | P1 |
| **Blog card** | Thumbnail + title + read time + arrow CTA | P3 |
| **Footer** | 4-column links + social + legal + brand mark | P1 |
| **Button (Primary)** | Filled papaya, hover darker, rounded `--br-100` | P1 |
| **Button (Secondary)** | Outlined or ghost, same dimensions | P1 |

### 3D. Animation Blueprint

| Animation | Element | Approach |
|-----------|---------|----------|
| Horizontal marquee | Asset tiles strip | CSS `@keyframes` + `animation: marquee 20s linear infinite` |
| Vertical marquee | Asset card columns | CSS `@keyframes` + `translateY`, reverse on second column |
| Typing effect | Code demo | JS character-by-character reveal |
| Scroll-driven pin | Pipeline steps (desktop) | CSS `position: sticky` per step |
| Section fade-in | All sections | `IntersectionObserver` → add class → CSS opacity + translateY |
| Stat counter | Numbers in community section | JS count-up on IntersectionObserver trigger |
| Navbar transition | Background opacity | Scroll listener → class toggle → CSS transition |
| Tab progress bar | Active tab indicator | CSS width animation over `N` seconds |
| Hover states | All interactive elements | CSS transitions, 0.2s ease |

> **No GSAP dependency** — we'll achieve all animations with CSS and lightweight vanilla JS. Keeps the build clean and fast.

### 3E. Layout System

- **Max content width:** 1280px centered, `padding: 0 --s-1400` (72px sides on desktop)
- **Section padding:** `--s-1400` (72px) top and bottom for major sections
- **Card grid:** CSS Grid, typically `repeat(3, 1fr)` → `repeat(2, 1fr)` → `1fr` at breakpoints
- **Breakpoints:**
  - Desktop: 1024px+
  - Tablet: 768px–1023px
  - Mobile: < 768px

---

## 4. Site Architecture

### Pages (Phase 1)

```
/ (Homepage)          ← Primary build, full story
/robotics             ← Use case deep-dive
/foundation-models    ← Use case deep-dive
/company              ← Team, mission, story
```

### Homepage Section Order

```
01. Navbar
02. Hero — "The data layer for Physical AI" + dual CTA
03. Social Proof Strip — logos + team count
04. Asset Showcase — horizontal marquee (3D assets by category)
05. Mission Statement — bold H2 + supporting paragraph
06. Code Demo — API snippet with typing animation
07. Pipeline — 5 steps: Ingest → Normalize → Augment → Validate → Deploy
08. Problem / Why Now — 4 stat blocks
09. Use Case Split — Robotics | Foundation Models
10. Data Validation Showcase — vertical marquee of asset variants
11. Methodology — 4-step approach grid
12. Community & Validation — validator count, QC rate, partnership
13. Final CTA — enterprise logos + dual buttons
14. Footer
```

---

## 5. Content Strategy (What We Need from the Team)

Before building, we need these content decisions:

| Item | Notes |
|------|-------|
| Hero headline | e.g. "The data layer for Physical AI" — confirm wording |
| Stat numbers | How many assets, validators, teams, pass rate — real or placeholder? |
| Client logos | Which logos can we show? Same as imagine.io's existing clients? |
| Use case names | "Robotics" + "Foundation Models" — same as reference or different? |
| Code snippet | What does the imagine.io API look like? Python preferred |
| Team/company copy | For /company page — team size, advisors, mission statement |
| Partnership badges | Any certifications, partnerships, data licenses to highlight? |

---

## 6. Build Order

| Phase | Deliverable | Output Path | Status |
|-------|-------------|-------------|--------|
| **0** | Tokens + Setup | `tokens.css`, `assets/` | ✅ Done |
| **1** | Homepage — static (no animations) | `outputs/homepage-v1.html` | ✅ Done |
| **2** | Homepage — light theme redesign | `outputs/homepage-v2.html` | ✅ Done |
| **2b** | Homepage — physicl.ai pattern overhaul + real images | `outputs/homepage-v3.html` | ✅ Done |
| **3** | /robotics page | `outputs/robotics-v1.html` | ⬜ Next |
| **4** | /foundation-models page | `outputs/foundation-models-v1.html` | ⬜ Pending |
| **5** | /company page | `outputs/company-v1.html` | ⬜ Pending |

---

## 7. Open Questions

| Question | Status | Decision |
|----------|--------|----------|
| Real vs. placeholder content? | ✅ Resolved | Real copy + logos from v1. Images: real product photos from `github.com/vipinmeena1468/library-assets` repo (added in v3). |
| Multi-page or single-page scroll? | ✅ Resolved | Separate HTML files per page. |
| Any pages to skip? | ✅ Resolved | Build all 4 pages. Homepage first (done), then /robotics, /foundation-models, /company. |
| Existing imagine.io assets? | ✅ Resolved | Using `library-assets` GitHub repo — product images across Furniture, Lighting, Apparel, and 12+ other categories. Accessed via `raw.githubusercontent.com`. |
| Primary CTA color — black (like physicl.ai) or papaya? | ✅ Resolved | **Papaya (`--papaya-500`)** — user confirmed. We keep brand color on CTAs for identity. |
| Icon library? | ✅ Resolved | **Material Symbols Outlined** (default). Fallbacks: Phosphor, then Lucide. Never mix. |
