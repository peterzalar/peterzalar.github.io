# Design: Add Media Appearances to Presentations Section

**Date:** 2026-03-01
**Scope:** `index.html` and `index.ja.html`

---

## Summary

Fold 8 media appearances from `master_cv.md` into the existing Presentations section. Rename the section "Presentations & Media" and append a subsection for media items using the existing badge and list pattern.

---

## Section Changes

### Heading
- `<h2>Presentations</h2>` → `<h2>Presentations & Media</h2>`

### Intro line
- Old: "32 presentations (24 invited) at international conferences and institutions."
- New: "32 presentations (24 invited) at international conferences and institutions; 8 media appearances and public engagement items."

### Structure after presentations `<details>` block
Add:
1. `<h3>Media & Public Engagement</h3>` subheading
2. `<ol reversed class="pub-list">` with 8 items, newest first, each ending with a type badge

---

## New Badge Types

Four new CSS variables and classes, following the existing pattern:

| Variable | Hex | Class | Label |
|---|---|---|---|
| `--badge-panel` | `#1565c0` | `badge-panel` | Panel |
| `--badge-interview` | `#00838f` | `badge-interview` | Interview |
| `--badge-feature` | `#ad1457` | `badge-feature` | Feature |
| `--badge-coverage` | `#37474f` | `badge-coverage` | Coverage |

---

## Media Entries (8 items, reverse chronological)

1. Invited Panelist, *Organic Electronics: Toward Bio- and Energy Applications* — iCanX Youth Talks. Aug 2023 `[Panel]`
   Link: https://youtu.be/Z87VO5DQK-0

2. Industry Interview, *Holst Centre: Electroactive Polymers* — IDTechEx. Jun 2023 `[Interview]`
   Link: https://archive.ph/nqJWd

3. Feature Article, *Progress in Elastomeric Large-Area Sensing Surfaces* — Organic & Printed Electronics Journal, Issue 41. Oct 2022 `[Feature]`
   Link: https://archive.is/O8Bce

4. Media Coverage, *Smart Sensor Mat for Heart Rate, Breathing Rate, and Posture Detection* — Organic & Printed Electronics Journal. Oct 2021 `[Coverage]`
   Link: https://archive.is/4JZ4U

5. Media Coverage, *TNO at Holst Centre Develops Smart Sensor Mat* — Printed Electronics Now. Oct 2021 `[Coverage]`
   Link: https://archive.is/JBOfM

6. Press Release, *TNO at Holst Centre Develops Smart Sensor Mat* — Holst Centre. Oct 2021 `[Coverage]`
   Link: https://archive.is/FGmla

7. Video Interview, *Peter Zalar – Get to Know TNO* — TNO YouTube Channel. Jan 2018 `[Interview]`
   Link: https://youtu.be/ihvWWRRlBiU

8. Profile Feature, *Meet Our Talents – Peter Zalar* — Brainport Eindhoven. Feb 2017 `[Feature]`
   Link: https://archive.ph/WqfYI

---

## Files to Edit

1. `index.html` — English page
2. `index.ja.html` — Japanese page (same structural changes; translate heading and intro)

---

## Out of Scope

- Navigation bar links (section ID `presentations` unchanged, so nav link still works)
- No new section ID needed
- Do not push to remote without explicit user approval
