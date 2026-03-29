# Media Appearances Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Fold 8 media appearances into the existing Presentations section on both the English and Japanese pages.

**Architecture:** Extend the existing `<section id="presentations">` in `index.html` and `index.ja.html`. Add 4 new CSS badge types, rename the section heading and intro, then append a `<h3>` subheading + `<ol>` media list after the existing presentations `<details>` block. No new sections, no nav changes (nav link reads "Talks" and stays as-is).

**Tech Stack:** Plain HTML/CSS. No build step. Open the file in a browser to verify visually.

---

### Task 1: Add new badge CSS variables and classes — `index.html`

**Files:**
- Modify: `index.html` (CSS block, lines ~93–99 for variables; lines ~310–316 for classes)

**Step 1: Add 4 new CSS custom properties**

Find this block (line ~99):
```css
      --badge-corresponding: #00695c;
```
Insert immediately after it:
```css
      --badge-panel: #1565c0;
      --badge-interview: #00838f;
      --badge-feature: #ad1457;
      --badge-coverage: #37474f;
```

**Step 2: Add 4 new badge classes**

Find this block (line ~316):
```css
    .badge-submitted { background: var(--badge-submitted); color: #fff; }
```
Insert immediately after it:
```css
    .badge-panel { background: var(--badge-panel); color: #fff; }
    .badge-interview { background: var(--badge-interview); color: #fff; }
    .badge-feature { background: var(--badge-feature); color: #fff; }
    .badge-coverage { background: var(--badge-coverage); color: #fff; }
```

**Step 3: Verify**

Open `index.html` in a browser. No visual change yet — just confirm the page still loads without errors.

---

### Task 2: Update section heading and intro — `index.html`

**Files:**
- Modify: `index.html` (lines ~652–653)

**Step 1: Update the heading**

Find:
```html
      <h2>Presentations</h2>
```
Replace with:
```html
      <h2>Presentations & Media</h2>
```

**Step 2: Update the intro paragraph**

Find:
```html
      <p class="section-intro">32 presentations (24 invited) at international conferences and institutions.</p>
```
Replace with:
```html
      <p class="section-intro">32 presentations (24 invited) at international conferences and institutions; 8 media appearances and public engagement items.</p>
```

**Step 3: Verify**

Reload `index.html` in browser. Section heading should now read "Presentations & Media".

---

### Task 3: Add media subheading and list — `index.html`

**Files:**
- Modify: `index.html` (after line ~692, the closing `</details>` tag of the presentations block)

**Step 1: Insert h3 and media list**

Find (line ~691–692):
```html
        </ol>
      </details>
    </section>
```
Replace with:
```html
        </ol>
      </details>

      <h3 style="margin: var(--space-6) 0 var(--space-4); font-size: 1rem; font-weight: 600; color: var(--text-primary);">Media &amp; Public Engagement</h3>
      <ol class="pub-list" reversed>
        <li>Invited Panelist, <em><a href="https://youtu.be/Z87VO5DQK-0" target="_blank" style="color:inherit;">Organic Electronics: Toward Bio- and Energy Applications</a></em> &mdash; iCanX Youth Talks. Aug 2023 <span class="badge badge-panel">Panel</span></li>
        <li>Industry Interview, <em><a href="https://archive.ph/nqJWd" target="_blank" style="color:inherit;">Holst Centre: Electroactive Polymers</a></em> &mdash; IDTechEx. Jun 2023 <span class="badge badge-interview">Interview</span></li>
        <li>Feature Article, <em><a href="https://archive.is/O8Bce" target="_blank" style="color:inherit;">Progress in Elastomeric Large-Area Sensing Surfaces</a></em> &mdash; Organic &amp; Printed Electronics Journal, Issue 41. Oct 2022 <span class="badge badge-feature">Feature</span></li>
        <li>Media Coverage, <em><a href="https://archive.is/4JZ4U" target="_blank" style="color:inherit;">Smart Sensor Mat for Heart Rate, Breathing Rate, and Posture Detection</a></em> &mdash; Organic &amp; Printed Electronics Journal. Oct 2021 <span class="badge badge-coverage">Coverage</span></li>
        <li>Media Coverage, <em><a href="https://archive.is/JBOfM" target="_blank" style="color:inherit;">TNO at Holst Centre Develops Smart Sensor Mat</a></em> &mdash; Printed Electronics Now. Oct 2021 <span class="badge badge-coverage">Coverage</span></li>
        <li>Press Release, <em><a href="https://archive.is/FGmla" target="_blank" style="color:inherit;">TNO at Holst Centre Develops Smart Sensor Mat</a></em> &mdash; Holst Centre. Oct 2021 <span class="badge badge-coverage">Coverage</span></li>
        <li>Video Interview, <em><a href="https://youtu.be/ihvWWRRlBiU" target="_blank" style="color:inherit;">Peter Zalar &ndash; Get to Know TNO</a></em> &mdash; TNO YouTube Channel. Jan 2018 <span class="badge badge-interview">Interview</span></li>
        <li>Profile Feature, <em><a href="https://archive.ph/WqfYI" target="_blank" style="color:inherit;">Meet Our Talents &ndash; Peter Zalar</a></em> &mdash; Brainport Eindhoven. Feb 2017 <span class="badge badge-feature">Feature</span></li>
      </ol>
    </section>
```

**Step 2: Verify**

Reload `index.html`. Confirm:
- "Media & Public Engagement" h3 appears below the presentations expand/collapse
- 8 items listed, newest first, numbered 8 down to 1
- Each item has a colored badge (blue=Panel, cyan=Interview, rose=Feature, dark gray=Coverage)
- All links open correctly

---

### Task 4: Commit English page changes

```bash
git add index.html
git commit -m "feat: add media appearances to presentations section (English)"
```

---

### Task 5: Mirror all changes to `index.ja.html`

**Files:**
- Modify: `index.ja.html` (same line numbers as `index.html` for CSS; same section structure)

**Step 1: Add CSS variables** (identical to Task 1 Step 1 — same insertion point)

**Step 2: Add CSS classes** (identical to Task 1 Step 2 — same insertion point)

**Step 3: Update heading**

Find:
```html
      <h2>発表</h2>
```
Replace with:
```html
      <h2>発表・メディア</h2>
```

**Step 4: Update nav link**

Find in the `<nav>` block:
```html
        <a href="#presentations">発表</a>
```
Replace with:
```html
        <a href="#presentations">発表・メディア</a>
```

**Step 5: Update intro paragraph**

Find:
```html
      <p class="section-intro">国際会議・研究機関での発表32件（うち招待講演24件）。</p>
```
Replace with:
```html
      <p class="section-intro">国際会議・研究機関での発表32件（うち招待講演24件）；メディア掲載・パブリックエンゲージメント8件。</p>
```

**Step 6: Add media subheading and list**

Find (same closing `</details>` block as `index.html`):
```html
        </ol>
      </details>
    </section>
```
Replace with:
```html
        </ol>
      </details>

      <h3 style="margin: var(--space-6) 0 var(--space-4); font-size: 1rem; font-weight: 600; color: var(--text-primary);">メディア・パブリックエンゲージメント</h3>
      <ol class="pub-list" reversed>
        <li>招待パネリスト、<em><a href="https://youtu.be/Z87VO5DQK-0" target="_blank" style="color:inherit;">Organic Electronics: Toward Bio- and Energy Applications</a></em> &mdash; iCanX Youth Talks. 2023年8月 <span class="badge badge-panel">Panel</span></li>
        <li>業界インタビュー、<em><a href="https://archive.ph/nqJWd" target="_blank" style="color:inherit;">Holst Centre: Electroactive Polymers</a></em> &mdash; IDTechEx. 2023年6月 <span class="badge badge-interview">Interview</span></li>
        <li>特集記事、<em><a href="https://archive.is/O8Bce" target="_blank" style="color:inherit;">Progress in Elastomeric Large-Area Sensing Surfaces</a></em> &mdash; Organic &amp; Printed Electronics Journal、第41号. 2022年10月 <span class="badge badge-feature">Feature</span></li>
        <li>メディア掲載、<em><a href="https://archive.is/4JZ4U" target="_blank" style="color:inherit;">Smart Sensor Mat for Heart Rate, Breathing Rate, and Posture Detection</a></em> &mdash; Organic &amp; Printed Electronics Journal. 2021年10月 <span class="badge badge-coverage">Coverage</span></li>
        <li>メディア掲載、<em><a href="https://archive.is/JBOfM" target="_blank" style="color:inherit;">TNO at Holst Centre Develops Smart Sensor Mat</a></em> &mdash; Printed Electronics Now. 2021年10月 <span class="badge badge-coverage">Coverage</span></li>
        <li>プレスリリース、<em><a href="https://archive.is/FGmla" target="_blank" style="color:inherit;">TNO at Holst Centre Develops Smart Sensor Mat</a></em> &mdash; Holst Centre. 2021年10月 <span class="badge badge-coverage">Coverage</span></li>
        <li>ビデオインタビュー、<em><a href="https://youtu.be/ihvWWRRlBiU" target="_blank" style="color:inherit;">Peter Zalar &ndash; Get to Know TNO</a></em> &mdash; TNO YouTubeチャンネル. 2018年1月 <span class="badge badge-interview">Interview</span></li>
        <li>プロフィール特集、<em><a href="https://archive.ph/WqfYI" target="_blank" style="color:inherit;">Meet Our Talents &ndash; Peter Zalar</a></em> &mdash; Brainport Eindhoven. 2017年2月 <span class="badge badge-feature">Feature</span></li>
      </ol>
    </section>
```

**Step 7: Verify**

Open `index.ja.html` in browser. Confirm same checks as Task 3 Step 2, plus Japanese labels render correctly.

---

### Task 6: Commit Japanese page changes

```bash
git add index.ja.html
git commit -m "feat: add media appearances to presentations section (Japanese)"
```

---

## Do Not

- Do not push to remote without explicit user approval
- Do not change the `id="presentations"` attribute (nav anchor still works)
- Do not change the English nav link "Talks" (it is intentionally shorter than the heading)
