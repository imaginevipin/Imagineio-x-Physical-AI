# physicl.ai — Design Reference & Observations

> **Purpose:** A living document recording all UX and visual design observations from physicl.ai. Updated every time we do a new round of analysis or reference new screenshots. Use this before every build iteration to stay aligned with what works.

**Last updated:** 2026-03-24
**Observed by:** Claude (UX Expert + Visual Design Director lens)

---

## 1. Overall Aesthetic Direction

| Attribute | physicl.ai |
|-----------|-----------|
| **Theme** | Light — off-white base (~#f0eeea), not pure white |
| **Font weight** | Heavy/bold for headlines (700–800). Confident, not elegant. |
| **Letter spacing** | Tight negative tracking on display type. Feels dense and editorial. |
| **Color** | Near-monochrome — black CTAs, grey text, off-white backgrounds. Brand accent (blue) used very sparingly. |
| **Border radius** | Generous on cards (~20px). Subtle on badges (pill/rectangle). |
| **Shadows** | Minimal to none. Structure comes from borders and background contrast, not elevation. |
| **Spacing** | Extremely generous vertical padding throughout. Every section breathes. |
| **Tone** | Authoritative, technical, restrained. Feels like a serious infrastructure company, not a startup. |

**Key takeaway:** The restraint is intentional. They never shout. The product does the talking through imagery and numbers.

---

## 2. Section-by-Section Observations

---

### 2A. Hero

**Screenshot observed:** Hero section with avatar social proof above headline.

**What they do:**
- Social proof sits *above* the headline — three avatar stacks + "187+ Teams satisfied." You see credibility before reading any copy. This is pre-headline trust, the most powerful placement on the page.
- Headline is extremely heavy weight (700–800), large, centered, with a period at the end. Reads like a definitive statement, not a tagline.
- Background is off-white (warm, not pure white) — premium and soft.
- Two CTA buttons: one filled **black** (not brand color), one outlined grey. No brand color on CTAs at all — restrained and confident.
- Very generous vertical padding above and below the headline block.

**Design principles at work:**
- Lead with social proof, not product description
- All-black CTA is more authoritative than colored buttons
- Period at the end of the headline signals finality and conviction

**What we're doing differently / should change:**
- Our social proof (stats) is in a strip below the fold. Move a single-line trust signal *above* the headline.
- ~~Our CTAs use papaya orange. Consider black as primary for authority.~~ **Decision (2026-03-24):** We keep papaya (`--papaya-500`) on primary CTAs — brand identity takes precedence over the black-CTA pattern. Secondary CTAs remain ghost/outlined.
- Our headline weight is 300 (light). Consider 400–500 for more gravitas.

---

### 2B. Code Demo + Asset Grid (layered composition)

**Screenshot observed:** Floating code editor window layered over a full-bleed grid of asset images.

**What they do:**
- The code demo is not a side-by-side layout. The code editor **floats above** real product imagery as a layered composition.
- Asset images fill the full background, edge-to-edge. Code panel sits centered on top.
- This single section communicates two things simultaneously: "here is real data at scale" (imagery) + "here is how you use it" (code). No scrolling required to make the connection.
- Asset image cards have:
  - Category pills bottom-left (e.g. "Living Room", "Sofa")
  - Variant counts bottom-right (e.g. "4,259+")
  - Status badges top-right ("Sim Ready", "Beauty Renders")
  - Real photography of 3D renders — warm-toned, realistic, desirable

**Design principles at work:**
- Depth and layering create visual interest without adding complexity
- Context-first: the data (images) grounds the code before you read a line of it
- Overlay labels on images > separate text rows below cards

**What we're doing differently / should change:**
- We have code demo and asset showcase as two separate sections. Merge into one layered composition.
- Our asset cards have a separate text row below the image. Switch to overlay labels *on top of* the image.
- Our placeholder images are plain black boxes. Even with placeholders, we should adopt the overlay label pattern to establish the visual language immediately.

---

### 2C. Use Cases — Nav Dropdown Cards

**Screenshot observed:** "Use Cases" nav item opens a dropdown with two large image cards (Robotics, Foundation Models).

**What they do:**
- Navigation itself is a product showcase. The dropdown shows two large cards with real imagery.
- Cards: large rounded corners (~20px), image fills top half completely edge-to-edge, no padding on the image.
- Bottom of card: "USE CASE" in tiny all-caps grey, then the name in large weight with icon left + arrow right.
- Clean, image-first, no description text needed.

**Design principles at work:**
- Use cases are shown, not explained, at the navigation level
- The image does the positioning work — a robotic hand for Robotics, a room scene for Foundation Models

**What we're doing differently / should change:**
- Our use case section uses text-heavy two-panel layout. Adopt image-first cards with overlay bottom label instead.
- Even with placeholder images, the card structure (image top, label overlay bottom) would feel significantly stronger.

---

### 2D. Pipeline Intro Headline

**Screenshot observed:** Full-width centered section with "One platform. Every step of the pipeline."

**What they do:**
- Enormous centered headline, period at the end. Full stop — no hedging.
- Small outlined pill badge above: "SOLUTION" — a bordered rectangle with tiny letter-spaced caps. Not a colored kicker, just a thin border. Extremely restrained.
- Subtitle writes the pipeline steps as inline prose: "Ingest → normalize → augment → validate → deploy. End-to-end data infrastructure, purpose-built for Physical AI training workflows."
- The section exists purely to anchor the user before showing pipeline detail. Acts as a chapter title.
- Massive vertical breathing room before and after.

**Design principles at work:**
- The bordered pill badge (no fill, just border + tiny caps) is more editorial and mature than a colored overline
- Writing the pipeline as a prose subtitle doubles its impact — you understand the flow before seeing the individual steps
- Chapter-title sections (text only, no components) create pacing and rest between dense sections

**What we're doing differently / should change:**
- Replace our colored "kicker" overlines with the bordered pill badge pattern.
- Add a pipeline intro section that is just the headline + prose flow before showing the step cards.

---

### 2E. Pipeline Steps — Vertical Stacked List

**Screenshot observed:** Pipeline steps as full-width stacked rows with dividing lines.

**What they do:**
- Each step is a full-width horizontal row. Rows are separated by thin dividing lines, not card borders.
- Each row: icon left | step number + title in medium weight | description text in grey.
- The active/first step is full-opacity black. Subsequent steps are progressively muted (lighter grey) — creates a sense of unfolding sequence.
- No background fill, no shadows, no rounded corners on the rows — pure typographic structure.

**Design principles at work:**
- Vertical stacking is scroll-friendly and doesn't compress at wide viewports
- Dividing lines as separators are more editorial than card borders
- Progressive opacity creates hierarchy and suggests sequence without animation
- The muted steps look like "coming next," building anticipation

**What we're doing differently / should change:**
- Our pipeline is a 5-column horizontal grid — it compresses and gets cramped. Replace entirely with this vertical stacked list.
- Apply progressive opacity: step 01 full black, steps 02–05 progressively lighter.
- Use thin `border-top` dividers between steps, not card borders.

---

### 2F. Approach / Methodology — 4 Flush Cards

**Screenshot observed:** "Physics is derived, not estimated." section with 4 horizontal cards in a flush row.

**What they do:**
- Centered headline with a bold claim + period. Then a supporting paragraph.
- Four equal-width cards in a flush horizontal row sharing only thin ruled dividers between them — no gap, no individual card borders, no box-shadows. They sit like columns in a table.
- Each card: "01. CATEGORY NAME" small caps label top-left | arrow → top-right | large title (~28px) | short subtitle | single badge pill at bottom.
- No visual noise. The structure is entirely typographic.

**Design principles at work:**
- Flush card strips with ruled dividers feel like data tables — appropriate for a data company
- Arrows on cards imply clickability / navigation without needing buttons
- Small-caps category + number in the top-left is a very clean information hierarchy pattern
- The bottom badge ("Fully structured", "Not estimated") acts as a mini proof point

**What we're doing differently / should change:**
- Replace our shadowed card grids with flush ruled strips where appropriate (especially pipeline, methodology, or tier sections).
- Adopt the "01. CATEGORY" + arrow top-left/right pattern for card headers.
- Add single-tag proof badges at card bottoms.

---

### 2G. Final CTA — Asymmetric Text + Image Grid

**Screenshot observed:** "Get the training data your models need." section with text left + live image grid right.

**What they do:**
- The section is split asymmetrically: ~40% text left, ~60% image grid right.
- Left: "CONTACT" pill badge | large heavy headline | short subtitle | two buttons (black filled + outlined grey)
- Right: a masonry-style grid of 3D render images — warm-toned room scenes. Images have "Verified" badges top-left, category labels and variant counts bottom overlaid.
- The image grid **bleeds to the right edge of the screen** — no container constraint on the right side. Creates a sense of abundance and overflow.
- The combination achieves three goals simultaneously: CTA, social proof via imagery, and product demonstration.

**Design principles at work:**
- Edge-bleeding images feel abundant — "we have more than we can even contain"
- Asymmetric left/right split is more dynamic than centered layouts
- "Verified" badges on images add trust at zero copy cost
- Doing CTA + imagery in one section earns attention that a text-only CTA never could

**What we're doing differently / should change:**
- Our final CTA is a centered papaya box — it's isolated and doesn't show the product. Replace with this asymmetric pattern.
- Text left, image grid right (with placeholder images for now), right side bleeds to edge.
- Add "Verified" badges to image cards throughout the site — including the placeholder versions.

---

## 3. Repeating Design Patterns (to adopt as a system)

These patterns appear across multiple sections and form the visual language of the site:

| Pattern | Description | Where they use it |
|---------|-------------|-------------------|
| **Bordered pill badge** | Thin border, no fill, tiny caps, letter-spaced. Acts as a section label. | Above headlines throughout |
| **Period at end of headline** | Every major headline ends with a full stop. Signals conviction. | Hero, pipeline, approach, CTA |
| **Overlay card labels** | Category, count, and status overlaid *on top of* images, not below. | Asset grid, CTA image grid |
| **Flush ruled strips** | Cards share dividing lines with no gap. No shadows, no individual borders. | Pipeline steps, approach cards |
| **Arrow → on cards** | Top-right arrow on every card implies navigation/depth. | Approach cards, use case dropdown |
| **Progressive text opacity** | Active state is black; subsequent/inactive states are grey. Creates sequence. | Pipeline steps |
| **Edge-bleeding imagery** | Image grids extend to screen edge, breaking the container. | Code demo section, final CTA |
| **Avatar stack + team count** | Three overlapping avatars + "N+ Teams satisfied." Always above the headline. | Hero |
| **"Verified" badge on images** | Small green checkmark + "Verified" label in top-left of image cards. | CTA image grid |
| **All-black CTAs** | Primary button is black, not brand color. Secondary is grey outlined. | Hero, CTA, use cases |

---

## 4. Typography Observations

| Element | physicl.ai approach |
|---------|-------------------|
| **Display / Hero H1** | ~80–96px, weight 700–800, tight letter-spacing (-2 to -3px), period at end |
| **Section headlines** | ~56–72px, weight 600–700, same tight tracking |
| **Card titles** | ~24–32px, weight 600, slightly tight |
| **Section labels** | 10–12px, weight 600, ALL CAPS, 2–3px letter-spacing, inside a thin-bordered pill |
| **Body / descriptions** | 15–17px, weight 400, colour ~#555–#777, generous line-height (1.65–1.75) |
| **Overlay labels on images** | 12–13px, weight 500, white or light colour, often on semi-transparent pill |
| **Numbers / counts** | Weight 700, same size as body or slightly larger, often in the same line as the label |

---

## 5. What physicl.ai Does NOT Do (also instructive)

- Does **not** use brand color (blue) on primary CTAs — they use black
- Does **not** have a dark/hero-dark section — 100% light throughout
- Does **not** use colored overlines/kickers — only bordered text pills
- Does **not** have gradient backgrounds or decorative shapes
- Does **not** use card box-shadows in most places — elevation comes from background contrast
- Does **not** center all their layouts — alternates between centered headers and asymmetric content sections
- Does **not** have emoji, icons-as-decoration, or visual clutter

---

## 6. What We Can Do Better Than physicl.ai

*(Unique strengths of imagine.io to amplify)*

1. **Application Tiers** (Perception / Navigation / Manipulation) — physicl.ai doesn't have a roadmap transparency story. This is a strong differentiator.
2. **10,000× variation multiplier** — more specific and compelling than physicl.ai's volume claims. Should be displayed as a primary stat, not buried.
3. **SOC 2 Type II** — physicl.ai doesn't mention enterprise compliance. We should surface this earlier.
4. **6+ years in production** — physicl.ai doesn't emphasise age/pedigree. "Not a research project" is excellent copy.
5. **150+ metadata attributes** — more granular than anything physicl.ai claims. Should get its own callout.

---

---

## 7. v3 Implementation Status

> Reviewed 2026-03-24 after `homepage-v3.html` build.

| Pattern | Implemented in v3? | Notes |
|---------|-------------------|-------|
| Avatar stack + team count above headline | ✅ Yes | Social proof row added above hero headline |
| Period at end of headlines | ✅ Yes | Applied to hero, pipeline, CTA, approach |
| Bordered pill badge (no fill) | ✅ Yes | Replaced all colored kicker overlines |
| Vertical stacked pipeline w/ ruled dividers | ✅ Yes | Progressive opacity: step 01 full, steps 02–05 fade |
| Code demo layered over asset image grid | ✅ Yes | Dark section — code panel floats over full-bleed image bg |
| Image-first use-case cards with overlay labels | ✅ Yes | uc-card pattern with overlay bottom label |
| Asymmetric CTA — text left, image grid right (edge-bleed) | ✅ Yes | ~40/60 split, right grid bleeds to edge |
| "Verified" badges on all image cards | ✅ Yes | Marquee cards, v-cards, cta-imgs all have Verified badge |
| Flush ruled methodology cards | ✅ Yes | Approach section uses flush strip with dividers |
| Real product images (not blank placeholders) | ✅ Yes | 38 placeholders replaced via `library-assets` GitHub repo |
| All-black primary CTAs | ❌ Skipped | **Decision:** keeping papaya (`--papaya-500`) for brand identity |

*Next review: before building /robotics inner page — check for any new patterns to adopt.*
