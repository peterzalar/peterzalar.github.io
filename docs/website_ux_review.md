# Website UX Review — www.peterzalar.com
*Updated: 2026-03-29 — fresh review of current state*

---

## What's Working Well

- Dark theme is cohesive; accent blue used consistently across interactive elements, badges, and highlights
- Timeline layout with glowing dot on current role reads immediately — the "PRESENT" badge is clear
- Collapsible experience bullets are a clean progressive-disclosure pattern
- Badge system on publications (First Author, Cover, Corresponding) adds meaningful signal at a glance
- Sticky nav with blur backdrop is polished
- JSON-LD structured data and hreflang for EN/JA are solid SEO foundations
- Section order (Experience → Education → Metrics → Publications) now flows logically

---

## Priority Issues

### 1. Nav links don't match the page — missing sections, wrong order
The nav shows: `About | Professional Experience | Publications | Patents | Talks | Education`

Problems:
- **Impact/Metrics, Expertise, and Languages have no nav entries** — a visitor can't jump to those sections
- **Education is listed last in the nav** but appears *before* Metrics and Publications in the DOM — a visitor following the nav would be confused by the scroll position jumping
- "Professional Experience" is long (17 characters) and wraps on mid-width screens; "Experience" alone is sufficient

Suggested nav order matching DOM: `About | Experience | Publications | Patents | Talks | Expertise | Languages`

### 2. About section opens by restating the hero
The hero already shows "Senior OLED Device Engineer at Apple." The first sentence of About is: *"I am currently a Senior OLED Device Engineer at Apple, focused on electrical modeling…"* — the visitor just read that. The About section should open with something that adds new information: the research thread, the Japan connection, or the career arc. Move the role restatement later in the paragraph or cut it.

### 3. Hero CTAs stack vertically — three pill buttons in a column
LinkedIn, Google Scholar, and Twitter/X render as three full-width stacked pills. This consumes significant vertical space before the visitor even starts reading. On desktop, these should be a horizontal inline row. Consider also whether "Twitter/X" still earns its place — if engagement is low, replacing it with a direct email or CV download link would serve visitors better.

### 4. "Details" label on every experience entry is generic
Every timeline entry uses the same "▶ Details" toggle. When scanning the timeline, this gives no contextual cue. "Responsibilities" or simply labeling by function ("Research scope", "Management scope") would let a recruiter decide which entries to expand before clicking. Alternatively, a one-line teaser sentence per role shown before the disclosure toggle would serve the same purpose.

### 5. No active/current section indicator on the sticky nav
There's no scroll-spy highlighting the current section in the nav. On a long single-page site this is basic orientation — without it, a visitor doesn't know where they are relative to the nav. A subtle `color: var(--text-primary)` or border-bottom on the active link would cost very little.

### 6. Long expandable lists have no visible way to collapse
"View all 40 publications" and "View all 32 presentations" are deep inline lists. Once expanded, a user must scroll far to reach the `<summary>` toggle again. A sticky "collapse" link at the bottom of each list, or simply an `id` anchor, would prevent the scroll trap.

---

## Layout & Visual Design

- **Expertise section uses heavy card-style bullets** — the global `ul li` style gives each expertise keyword a bordered card with hover animation. This makes skills feel interactive/clickable when they're just labels. Tag/chip styling (inline, no hover movement) would be more appropriate for a keyword taxonomy
- **Languages section is orphaned at the bottom**, after Expertise. Given the Japan connection and multilingual profile, this could be positioned near the About section where it reinforces Peter's personal brand
- **Section hover effect** (border brightens on `.section:hover`) is subtle to the point of being unnoticeable on dark backgrounds — consider increasing border contrast on hover or removing it to simplify
- **Footer "Last updated: February 2026"** is stale — now March 2026

---

## Content Gaps

- **No downloadable CV or resume link** — academic and industry visitors frequently want a PDF. A subtle "Download CV" link in the hero or nav would reduce friction for this common request
- **h-index of 25 is not explained** — industry visitors (not from academia) won't know what h-index means. A tooltip or a small parenthetical ("h-index 25 — a measure of publication impact") would help
- **Publications section title** says "First-Author Highlights" but the section also contains the full pub list. The title could be "Publications" with a subhead for the highlights

---

## Accessibility

- **No visible `:focus` styles on most interactive elements** — keyboard navigation produces no visible focus ring outside the nav. At minimum, links and `<summary>` elements need `:focus-visible` outlines
- **Badge colors still convey status without text fallback** — colorblind users cannot distinguish Granted (green) vs. Pending (orange) vs. Submitted (grey) if color perception is impaired. The text labels already partially address this, but badge colors for similar hues (Interview `#00838f` vs. Corresponding `#00695c`) are very close
- **`<details>` summary elements** lack `aria-expanded` — screen readers may not announce state correctly across all browsers

---

## Summary Table

| # | Issue | Severity | Effort |
|---|-------|----------|--------|
| 1 | Nav missing sections + order mismatch | High | Low |
| 2 | About section repeats hero subtitle | Medium | Low |
| 3 | Hero CTAs stacked vertically | Medium | Low |
| 4 | "Details" toggle label is generic, not scannable | Medium | Low |
| 5 | No scroll-spy active state on nav | Medium | Medium |
| 6 | Expanded lists have no collapse affordance at bottom | Medium | Low |
| 7 | Expertise uses card-style for keyword tags | Low | Low |
| 8 | Languages misplaced at page bottom | Low | Low |
| 9 | No CV download link | Low | Low |
| 10 | Footer "last updated" date is stale | Low | Low |
| 11 | Focus styles missing on interactive elements | Medium | Low |
