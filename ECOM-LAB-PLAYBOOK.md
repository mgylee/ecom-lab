# Ecom Lab Playbook

How to write, design, and publish a Gorgias Ecommerce Lab report. This document captures every decision made across Reports 1-3 so any team member can replicate the format.

---

## What is Ecom Lab

A series of editorial, data-driven research reports published at ecom-lab-j64e.vercel.app. Inspired by Ramp Economics Lab. Each report takes one finding from Gorgias platform data and builds a tight argument around it.

**Audience:** Hesitating CX/ecom leaders (VPs, Directors, C-suite) who haven't committed to AI or are benchmarking their operations.

**Published reports:**
- Report 1: AI Adoption Index — `report-01-ai-adoption-index` — **Finalized**
- Report 2: Support Economics — `report-02-support-cost` — **In progress** (2 [NEED] remaining)
- Report 3: CX Benchmarks — `report-03-cx-benchmarks` — **Finalized**

**Live URL:** ecom-lab-j64e.vercel.app
**Notion archive:** [Ecom Finalized Content](https://www.notion.so/gorgias/Ecom-Finalized-Content-32c1ae2178f580aa9431dd878ef73a05)

---

## Tone of Voice

### The rules
- **Direct.** Make a strong claim. Back it with data. Move on.
- **One stance per report.** No hedging, no "on the other hand." Pick a side.
- **Let data speak.** Do not editorialize. Do not say "impressive" or "remarkable." The numbers are the argument.
- **No conflicting points.** If a data point undermines your stance, either address it head-on or remove it. Do not leave holes for the reader to poke.
- **Short sentences.** Active voice. Peer-to-peer, not consultant-speak.

### What to avoid
- No em dashes ( — ). Use periods or commas.
- No sample sizes or brand counts (private data).
- No "SMB" / "Enterprise" labels. Use GMV ranges ($5M, $150M).
- No superlatives: "impressive," "remarkable," "powerful," "robust."
- No salesy CTAs: "Book a demo," "Get started," "Learn more."
- No emojis.
- Do not mention how many brands are in the sample.
- Do not use "Gorgias AI" or "bot." Use "AI Agent" (official product name).

### What to do
- Use GMV-based framing throughout ($5-30M GMV, not "mid-market").
- Round numbers for readability (19.8 hrs, not 19.79342 hrs).
- When a metric could be misleading, use median over average and explain why in methodology.
- Include a methodology section at the bottom of every report.
- Flag data that needs validation with `[NEED: description]` placeholders.

---

## Report Structure

Every report follows this skeleton:

```
# Title. [Strong claim, one sentence.]

*Gorgias Ecommerce Lab | [Month Year]*

---

**[Stat 1]** [one-line description]
**[Stat 2]** [one-line description]
**[Stat 3]** [one-line description]

---

## [Section 1 — set up the problem]
## [Section 2 — show the data]
## [Section 3 — deepen or expand]
## [Section 4 — (optional) how to use / what it means]
## The bottom line

---

**Methodology:** [How data was collected, what was measured, caveats, date.]
```

### Title
- One sentence. Strong claim. No subtitle.
- Pattern: "[Provocative claim]." or "[Claim]. [Qualifier]."
- Examples: "Most brands are overpaying for support. Here's the math." / "Stop benchmarking against the average."

### Stat strip
- Exactly 3 stats.
- Large number + one-line description.
- Numbers should be immediately meaningful without reading the report.
- Avoid stats that require context (e.g., "6.25" without explanation). Prefer framing ("2x" instead of "6.25 agents").

### Sections
- 3-5 sections max. Fewer is better.
- Each section has one point. Make it, show the data, move on.
- No more than 2 paragraphs of prose per section before a chart or table.

### The bottom line
- 1-2 paragraphs.
- Restate the stance. No new data.
- End with a forward-looking statement, not a CTA.

### Methodology
- Always include.
- Explain data source, time period, metric definitions, and any filters.
- Note why median vs. average was chosen if applicable.
- Note any filtering (e.g., "accounts with net positive savings").

---

## Data Standards

### Before writing
1. Confirm metric definitions with the data team.
2. Check whether data is human-only, AI-only, or blended.
3. Identify the strongest single finding. Build the report around that.
4. Pressure-test: can any data point in the report be used to contradict the stance? If yes, address it or remove it.

### During writing
- If data is missing, use `[NEED: description]` placeholder. Do not guess.
- If a correlation claim is directional but not clean, say "directional" not "drives" or "causes."
- Include net figures where possible (e.g., savings minus platform cost).
- Do not claim causation from cross-sectional data.

### Data that must be validated
- Cost per ticket methodology
- Repeat rate definition (ever contacted vs. same issue vs. time window)
- Resolution time scope (human, AI, or blended)
- Any metric with the word "average" — confirm whether mean or median

---

## Design System

### Typography
- **Headings:** Playfair Display 700 (serif)
- **Body:** Inter 400/500/600 (sans-serif)
- Google Fonts import: `Playfair+Display:wght@700` + `Inter:ital,wght@0,400;0,500;0,600;1,400`

### Color palette (zinc monochrome + accent)
```
--black:   #0A0A0A
--900:     #18181B
--700:     #3F3F46
--500:     #71717A
--400:     #A1A1AA
--200:     #E4E4E7
--100:     #F4F4F5
--50:      #FAFAFA
--white:   #FFFFFF
--accent:  #FF5B35  (orange, use sparingly)
```

### Accent usage
- 3px orange top border on page (body::before)
- Nav brand dot
- Highlight cells in tables (`.td-accent`)
- Chart emphasis (highest/lowest bar, key data point)
- Do NOT use accent for body text, backgrounds, or borders

### Layout
- Two-column CSS Grid: content column (680px) + sidebar (240px)
- Sticky nav (52px, blurred background)
- Sticky sidebar TOC on scroll
- Max-width container: `calc(680px + 240px + 80px)`
- Responsive: single column below 900px, sidebar hidden

### Components

**Nav bar:** Logo dot + "Gorgias Ecommerce Lab" left, "Research" label right.

**Header section:** Eyebrow tags (topic + date), H1 title, deck paragraph, author row (avatar initials + name + title). Sidebar with TOC, subscribe box, share buttons.

**Stats strip:** 3-column grid below header. Large Playfair number + Inter description. Bordered between items.

**Charts (Chart.js 4.4.0):**
- Contained in `.chart-block` (border, rounded corners)
- Header: title + subtitle
- Chart area: responsive, specific height per chart
- Footer: source attribution
- Bar charts: zinc gradient (light to dark) with accent for emphasis
- Line charts: zinc for baseline, accent for key line
- Tooltips: custom label callbacks
- Grid: `#F4F4F5`, no borders

**Tables (`.data-table`):**
- Uppercase headers, small font, letter-spaced
- Clean row borders (`--100`)
- `.td-bold` for labels, `.td-accent` for highlighted values
- No zebra striping

**Methodology block:** Light background (`--50`), small text, rounded border.

**Feedback button:** Fixed bottom-right, links to Google Form (not mailto). `<a>` tag, not `<button>`.

### Chart types used
| Chart type | When to use | Example |
|-----------|-------------|---------|
| Horizontal bar | Comparing verticals/categories | Resolution time by vertical |
| Vertical bar | Time series or sequential tiers | Tickets per agent by GMV |
| Line (dual) | Showing crossover or divergence | Human team vs AI equivalents |
| Combo (bar + line) | Showing correlation between metrics | Repeat rate bars + resolution line |
| Custom HTML bars | When scale difference is extreme | Human vs AI resolution time |

---

## Publishing

### File structure
```
ecom-lab/
  index.html                          # Root (copy of Report 1)
  report-01-ai-adoption-index.html
  report-01-ai-adoption-index.md
  report-02-support-cost.html
  report-02-support-cost.md
  report-03-cx-benchmarks.html
  report-03-cx-benchmarks.md
  vercel.json                         # { "cleanUrls": true }
  ECOM-LAB-PLAYBOOK.md               # This file
```

### Naming convention
- `report-[##]-[slug].html` and `.md`
- Slug: lowercase, hyphenated, 2-4 words

### Deploy
- GitHub repo: `mgylee/ecom-lab`
- Auto-deploys to Vercel on push to `main`
- Vercel project: `ecom-lab-j64e`
- URLs: `ecom-lab-j64e.vercel.app/report-[##]-[slug]`
- `cleanUrls: true` in vercel.json removes `.html` extensions

### Workflow
1. Write .md first (content and data)
2. Build .html using design system
3. Both files must stay in sync
4. Commit and push to `main`
5. Vercel auto-deploys

### Feedback
- Floating button on every report links to Google Form
- Form URL: `https://docs.google.com/forms/d/e/1FAIpQLSeIS0YgyVSuwy1ZailiGB9chENZE6fILkyFbeZi_jGiRswgSg/viewform`

---

## Data Directory

All report data must trace back to a validated source. Every chart and table should include a source link in the footer.

### Primary sources

| Source | What it covers | Link |
|--------|---------------|------|
| Airtable (appHTPnidve5znze0) | CX benchmarks by GMV and automation rate: FRT, resolution time, CSAT, tickets/100 orders, AI adoption rate, agent equivalents across 14 verticals | [Airtable](https://airtable.com/appHTPnidve5znze0) |
| Finalized Data Sources (Notion) | Metric definitions, SQL queries, smoothing methodology, pipeline documentation | [Notion](https://www.notion.so/gorgias/Ecom-Lab-Finalized-Data-Sources-3281ae2178f58067a241c98c38d93a47) |
| ROI of AI: Support Agents (Notion) | FRT before/after, YoY efficiency by automation tier, headcount reduction, hours/1K tickets | [Notion](https://www.notion.so/gorgias/ROI-of-AI-Support-Agents-30b1ae2178f580acbfbcfa9918a0d46d) |
| EcomLab Report First Data (Notion) | Adoption trend (monthly), agent equivalents, productivity, headcount savings, ROI by automation tier | [Notion](https://www.notion.so/gorgias/EcomLab-Report-First-Data-2ee1ae2178f58028a99ceafe261e5119) |

### Source of truth

**Airtable is the source of truth for all CX benchmark data** (Reports 1 and 3). CSV exports from the same pipeline may have different values due to re-runs with updated data. Always validate against the Airtable, not downloaded CSVs.

Report 2 uses separate datasets (ROI analysis, headcount reduction) that are documented in the Notion pages above but not in the Airtable.

### Report data status

| Report | Data status | Remaining [NEED] |
|--------|------------|-------------------|
| Report 1: AI Adoption Index | Fully validated against Airtable | None |
| Report 2: Support Economics | Mostly validated | Tickets per agent by GMV tier, resolution time before/after |
| Report 3: CX Benchmarks | Fully validated against Airtable | None |

### Finalized content

All three reports are archived in Notion: [Ecom Finalized Content](https://www.notion.so/gorgias/Ecom-Finalized-Content-32c1ae2178f580aa9431dd878ef73a05)

### Key assumptions

- Agent cost: $20K/year blended (weighted average of US-based and offshore support hires)
- Platform cost: $9K/year average
- AI adoption: requires activation + at least 5% automation in a 7-day period with at least 5 billed tickets
- Benchmark window: last 90 days minus 7-day billing lag
- Minimum account threshold: 30 tickets
- Smoothing: Gaussian kernel, bandwidth 0.4 (log10 GMV) / 8 (automation rate pct)

---

## Lessons Learned

1. **Start with one stance, not the data.** The best reports started with a clear claim and selected data to support it. The worst iterations tried to let the data "speak for itself" — it doesn't, it just creates noise.

2. **Pressure-test before writing.** Walk through every data point and ask: "Can this be used to argue against my stance?" If yes, either address it head-on in the prose or cut it. Do not leave holes.

3. **Less is more.** Report 2 went from 5 tables + 3 charts to 1 table + 2 charts. The tighter version was stronger. Default to cutting.

4. **Avoid correlation claims unless the data is clean.** "FCR drives CSAT" sounded right but the data had too many exceptions. "Directional" is honest. "Drives" is a claim you need to defend.

5. **Net over gross.** Readers will immediately ask "but what does it cost?" Include platform costs in savings figures. Show net, not gross.

6. **GMV framing, not company labels.** "$5-30M GMV" is what the reader identifies with. "Commercial" or "mid-market" is internal Gorgias segmentation that means nothing to them.

7. **Median over average when distributions are skewed.** AI Agent averages are skewed by 72-hour auto-timeouts. Always check whether mean or median is the honest signal, and note the choice in methodology.

8. **The stat strip number must be instantly clear.** "6.25" as a stat is confusing. "2x" is not. If the number needs a paragraph of context, it is the wrong number for the stat strip.

9. **Don't force a narrative.** Report 3 went through 5 rewrites because we kept trying to find a causal story in data that only showed directional patterns. The final version worked because it stopped claiming causation and instead gave the reader a useful tool (their vertical benchmark).

10. **Feedback widget must actually work.** Mailto links depend on the user's email client. Google Forms always work. Use Forms.
