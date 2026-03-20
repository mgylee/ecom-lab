# Ecom Lab Editorial Log

How Matilda thinks about data narratives. Captured from the editorial process across Reports 1-3. This is a reference for anyone collaborating with her on future reports.

---

## How she evaluates a narrative

### The first question is always: "What's the one stance?"
Every report needs a single, defensible claim. If you can't state it in one sentence, you don't have it yet. She will push back until it's sharp.

### Data must be unchallengeable
Her standard: "Data should be consistent and cannot be challenged or poked." This means:
- Every number in the report must come from a verified source
- No data point should contradict the stance
- If a correlation is directional but not clean, do not claim causation
- If data is missing, use a placeholder. Do not fill gaps with assumptions.

### She will kill a narrative that doesn't hold up
Report 3 went through 5 complete rewrites. Each time, she identified a weakness in the argument and pivoted rather than publish something with holes. The sequence:
1. "Vertical predicts automation outcomes" — killed because the 5x claim didn't match the listed data
2. "Your CSAT score is lying to you" — killed because FCR-to-CSAT correlation had too many exceptions
3. "Speed drives satisfaction" — killed because the middle of the dataset was messy (only extremes correlated)
4. "More than half your tickets are repeats" — killed because the action item was too weak ("track repeat rate" isn't actionable enough)
5. "Stop benchmarking against the average" — shipped because the data was clean, the stance was unchallengeable, and it gave the reader something useful (their actual benchmark)

The lesson: she would rather restart than ship something with a hole in it.

### She separates "interesting" from "publishable"
Many findings from the data were interesting but not strong enough to build a report around:
- NPS varies more than CSAT (interesting, but "more variance" doesn't mean "better signal")
- FCR loosely tracks CSAT (interesting, but Apparel at 43.4% FCR / 4.39 CSAT breaks it)
- Electronics is worst on every metric (interesting, but too narrow for a standalone report)

Her filter: can you make the claim without qualifying it? If you have to say "except for..." more than once, it's not ready.

---

## Narrative decisions she made

### Report 1: AI Adoption Index
- **Original framing included a "ceiling" on automation.** She cut it. The audience is hesitating leaders. Telling them there's a ceiling undermines the case for adopting.
- **Removed all references to brands that bought AI but aren't automating.** Wanted the contrast to be between adopters and non-adopters, not between good and bad adopters.
- **"Let the data speak"** was a direct instruction. No editorializing, no "impressive," no persuasion. The numbers are the argument.

### Report 2: Support Economics
- **Reframed "replacing agents" as "scaling without hiring."** Her instinct: the audience (CX leaders) doesn't want to hear about replacing their team. They want to hear about scaling without growing headcount. Same data, different framing.
- **Added net savings (minus platform cost).** Feedback said gross savings without cost of AI is not credible. She agreed immediately. Always show net.
- **Changed stat strip from "6.25" to "2x."** The raw number was confusing without context. "2x" is instantly clear. Stat strip numbers must stand alone.
- **"SMB" and "Enterprise" replaced with GMV ranges.** Her logic: a $5-30M brand doesn't call itself "Commercial." Use the language the reader uses for themselves.
- **Median over average for AI resolution time.** The 72-hour auto-timeout skews the mean. She asked the right question ("should we use average?"), then accepted the reasoning for median when the distortion was explained.

### Report 3: CX Benchmarks
- **Rejected the first draft from her team.** It was too long (2,000+ words), repeated the same point 5 times, used em dashes, mentioned brand counts, and had salesy CTAs. All violations of the established format.
- **Rejected the "CSAT is lying" angle after pressure-testing.** When pushed, the data showed CSAT does loosely correlate with speed at the extremes. "Lying" was too strong a claim for directional data.
- **Rejected forced correlation narratives.** When shown that FCR-to-CSAT and speed-to-CSAT both had exceptions, she asked: "Can you look at the data with an objective, non-biased mindset?" She wanted honest pattern recognition, not narrative confirmation.
- **Flagged the 60% automation conflict.** The benchmark data showed 10-17% automation rates. Publishing that would contradict the product's "60% automation" claim. She caught this before it went live.
- **Settled on a framework angle.** Instead of claiming a causal relationship, the final report gives the reader a tool: your vertical benchmark. This avoids correlation claims entirely and is genuinely useful.

---

## Her editorial instincts

1. **She thinks about what the reader will do with the information.** "What's the action item?" is a recurring question. If the report doesn't change a decision or behavior, it's not ready.

2. **She protects the brand.** The 60% automation flag was about credibility. Publishing conflicting data in your own research undermines the product story.

3. **She prefers reframing over cutting.** "Replacing agents" became "scaling without hiring." Same data, same conclusion, different emotional response from the reader.

4. **She values honesty over cleverness.** When the data didn't support a narrative, she didn't try to spin it. She pivoted. Five times on Report 3.

5. **She pushes for specificity.** "Enterprise brand" became "$150M+ GMV." "Resolves" became "handles billable tickets." "Average" needed clarification on whether it was mean or median.

6. **She benchmarks against the reader's skepticism.** Every claim is evaluated through the lens of "would a skeptical VP poke a hole in this?" If yes, fix it before publishing.

7. **She separates data exploration from narrative writing.** The process was: look at data objectively first, identify what's clean and consistent, then build the stance. Not the other way around.

8. **She knows when to stop.** Report 3 could have been rewritten a sixth time. Instead, she settled on the version where the data was clean and the reader got something useful. Shipping a good report beats perfecting an uncertain one.

---

## Process that worked

1. Start with raw data. Look at it objectively. No narrative yet.
2. Identify what patterns are consistent (no exceptions) vs. directional (some exceptions).
3. Build the stance around the consistent pattern only.
4. Write the .md first. Get alignment on content and data.
5. Build the .html using the design system.
6. Pressure-test: walk through every data point and ask "can this be challenged?"
7. Get feedback. Address it. Do not dismiss valid pushback.
8. Ship when the data is clean and the stance is unchallengeable.

---

## Questions to ask before writing any new report

1. What is the one stance? Can you say it in one sentence?
2. Is every data point in the report consistent with that stance?
3. Can any number be used to argue against you?
4. What will the reader do differently after reading this?
5. Does anything in this report conflict with Gorgias product positioning?
6. Are you using the right metric (mean vs. median, gross vs. net)?
7. Have you confirmed metric definitions with the data team?
8. Would a skeptical VP find a hole in this?
