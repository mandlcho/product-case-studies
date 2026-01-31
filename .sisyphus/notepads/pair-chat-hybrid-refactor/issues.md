# Issues & Gotchas: Pair Chat Hybrid Refactor

## Known Issues

### Issue 1: Dense Slides Identified
**Slides violating "One Breath Rule" (>50 words body text):**
1. "How I Discovered This" - 3 quotes + setup + synthesis (~150 words)
2. "How I Arrived at This Insight" - Case study analysis + aha moment (~120 words)
3. "How I Decided" - Decision framework with 3 criteria (~140 words)
4. "First 30 Days: Week-by-Week" - 4 weeks of tactical breakdown (~180 words)
5. "The Core Insight" slide - Multiple paragraphs (~100 words)

**Action Required:** Split each into 3-5 focused slides.

### Issue 2: Key Insights Buried
**Current problems:**
- "47% activation gap" mentioned in paragraph, not hero text
- "Trust is the unlock" appears late, not emphasized
- "Platform signal" (20,000 AIBots) not visually dominant
- Decision criteria hidden in bullet points

**Action Required:** Extract as HERO text (3-4em font size).

### Issue 3: Slide Count Will Increase
**Current:** 21 slides (including appendix)
**Estimated after refactor:** 30-35 slides
**Concern:** Presentation might feel too long
**Mitigation:** 
- More slides ≠ longer presentation (each slide is faster to read)
- Target: 20-30 seconds per slide = 10-12 minutes total
- Test delivery time in Task 3.2

## Gotchas to Watch For

### Gotcha 1: HTML Slide Navigation
**Problem:** HTML uses scroll-snap for navigation. Adding slides changes scroll positions.
**Watch for:** Navigation dots count, keyboard navigation, progress bar calculation.
**Solution:** Update JavaScript slide count after adding new slides.

### Gotcha 2: Reveal Animations
**Problem:** HTML uses `.reveal` class with staggered delays (nth-child selectors).
**Watch for:** Too many reveal elements on one slide = long animation time.
**Solution:** Limit to 4-5 reveal elements per slide max.

### Gotcha 3: Markdown → HTML Sync
**Problem:** Markdown uses `---` for slide breaks. HTML uses `<section class="slide">`.
**Watch for:** Slide count mismatch between files.
**Solution:** Count slides in both files during Task 3.1 verification.

### Gotcha 4: Callout Box Overuse
**Problem:** Current HTML has many callout boxes. Adding more could dilute impact.
**Watch for:** Every slide having a callout = nothing stands out.
**Solution:** Reserve callouts for truly critical points only.

### Gotcha 5: Font Size Responsiveness
**Problem:** CSS uses `clamp()` for responsive font sizes. Changing base sizes affects mobile.
**Watch for:** Hero text (3-4em) might be too large on mobile.
**Solution:** Test responsive behavior in Task 3.2. Adjust clamp() ranges if needed.

## Questions to Resolve

### Q1: How to Handle Week-by-Week Timeline?
**Current:** Single slide with 4 timeline items (Week 1-4).
**Options:**
- A) Keep as single slide (timeline format is scannable)
- B) Split into 4 slides (one per week)
- C) Split into 2 slides (Week 1-2, Week 3-4)
**Recommendation:** Option A - timeline format is already visual and scannable. Splitting would break narrative flow.

### Q2: Should Appendix Slides Be Refactored?
**Current:** 3 appendix slides (competitive positioning, metrics, questions).
**Options:**
- A) Leave as-is (appendix is backup material, density is acceptable)
- B) Apply visual hierarchy but don't split
- C) Full refactor like main slides
**Recommendation:** Option B - apply visual hierarchy for consistency, but don't split (appendix is reference material).

### Q3: How to Handle Quote Slides?
**Current:** Quotes in callout boxes with context.
**Options:**
- A) One quote per slide (very focused)
- B) Quote + minimal context on same slide
- C) Setup slide → quote slide → synthesis slide
**Recommendation:** Option B for most quotes, Option C for "How I Discovered This" section (3 quotes need setup + synthesis).

## Patterns to Follow

### Pattern 1: Hero Insight Slides
```
[HERO TEXT - 3-4em, bold, accent color]
47% Activation Gap

[Context - 1.5em]
70,000 officers signed up but never activated

[Meta - 0.9em]
That's $8.7M in untapped monthly value
```

### Pattern 2: Quote Slides
```
[Setup - 1.5em]
From a policy officer at MOH:

[Quote - 1.2em, italic, callout box]
"I signed up because my boss told me to. But I've never logged in..."

[Takeaway - 1em, bold]
Pattern: Trust barrier
```

### Pattern 3: Decision Framework Slides
```
[Title - 2em]
How I Decided

[Criteria - 1.5em, numbered list]
1. Time to Impact
2. Risk
3. Compounding Effects

[Next slide: Details for each criterion]
```

## Issue 4: Subagent Failure on Markdown Restructure
**Task:** Task 1.1 - Restructure markdown presentation
**Agent:** Sisyphus-Junior (category: writing)
**Problem:** Agent returned "completed" twice but made no file changes
**Evidence:**
- First invocation: session ses_3f0d29647ffe8SkDV6dTp8ZfYe - no output, no changes
- Second invocation (resume): same session - no output, no changes
- File remained unchanged after both attempts
**Resolution:** Orchestrator completed task directly using Edit tool
**Lesson:** Writing category agent may have issues with large file restructures. Consider breaking into smaller edits or using different approach.
