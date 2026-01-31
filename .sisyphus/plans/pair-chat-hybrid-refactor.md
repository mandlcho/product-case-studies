# Pair Chat Presentation: Hybrid Refactor Plan

## Goal
Transform the Pair Chat presentation using a hybrid approach:
1. **Restructure narrative** to lead with adoption problem (maintain strategic depth)
2. **Apply visual hierarchy** using "One Breath Rule" (split dense slides, increase key insight font sizes)

## Success Criteria
- [ ] Presentation leads with 47% activation gap as THE core problem (upfront, not buried)
- [ ] All slides pass "One Breath Rule" (~15 seconds to read, 30-50 words body text max)
- [ ] Visual hierarchy implemented: Hero (3-4em), Context (1.5-2em), Meta (0.9-1em)
- [ ] Dense slides split appropriately (e.g., "How I Discovered This" → 5 slides)
- [ ] Strategic depth preserved (3 signals, 3 options, decision framework)
- [ ] Both markdown and HTML files updated and in sync
- [ ] Total presentation time: 10-12 minutes when delivered

## Constraints
- Maintain monospace aesthetic (JetBrains Mono + IBM Plex Mono)
- Keep animated gradient backgrounds
- Preserve all interview-centric content (user empathy, decision-making, vulnerability)
- Don't cut content—reformat and redistribute

---

## Task Breakdown

### Phase 1: Restructure Narrative (Adoption-First)

**Parallelizable:** No (sequential restructure required)

- [ ] **Task 1.1: Restructure markdown presentation**
  - Lead with adoption problem (47% activation gap) immediately after hook
  - Reorder sections to follow hybrid structure:
    1. Hook + Core Problem Stated
    2. Context (what is Pair Chat)
    3. Evidence (3 Signals) - prove why adoption gap is critical
    4. Root Cause Diagnosis (trust + discoverability)
    5. Strategic Options (3 options evaluated)
    6. Recommended Path (A + C with decision framework)
    7. 30/60/90 Execution
    8. Close with vulnerability
  - Preserve all existing content, just reorder
  - **Files:** `presentation-pair-chat.md`
  - **Effort:** 1-2 hours
  - **Dependencies:** None

- [ ] **Task 1.2: Update HTML to match restructured narrative**
  - Reorder HTML slides to match new markdown structure
  - Ensure slide numbers and navigation dots align
  - **Files:** `presentations/pair-chat-presentation.html`
  - **Effort:** 30 minutes
  - **Dependencies:** Task 1.1 complete

### Phase 2: Apply Visual Hierarchy

**Parallelizable:** No (requires restructure to be complete first)

- [ ] **Task 2.1: Split dense slides in markdown**
  - Identify slides violating "One Breath Rule" (>50 words body text)
  - Split into multiple slides with clear breaks
  - Priority targets:
    - "How I Discovered This" (3 quotes) → 5 slides
    - "How I Arrived at This Insight" → 3-4 slides
    - "How I Decided" (decision framework) → 2-3 slides
    - "First 30 Days Week-by-Week" → Keep timeline format but reduce text density
  - Add slide break markers in markdown
  - **Files:** `presentation-pair-chat.md`
  - **Effort:** 2-3 hours
  - **Dependencies:** Task 1.1 complete

- [ ] **Task 2.2: Implement visual hierarchy in HTML**
  - Update CSS for 3-tier typography system:
    - Hero insights: 3-4em font size, bold, accent color
    - Context text: 1.5-2em font size
    - Meta information: 0.9-1em font size
  - Split dense HTML slides to match markdown
  - Increase white space between elements
  - Make key metrics and insights visually dominant
  - Test "One Breath Rule" on each slide
  - **Files:** `presentations/pair-chat-presentation.html`
  - **Effort:** 3-4 hours
  - **Dependencies:** Task 2.1 complete

### Phase 3: Verification & Polish

**Parallelizable:** No (final verification)

- [ ] **Task 3.1: Verify sync between markdown and HTML**
  - Manually compare slide-by-slide
  - Ensure content matches
  - Check slide count alignment
  - **Files:** Both files
  - **Effort:** 30 minutes
  - **Dependencies:** All previous tasks complete

- [ ] **Task 3.2: Test presentation delivery**
  - Open HTML in browser
  - Navigate through all slides
  - Verify animations work
  - Test keyboard navigation
  - Verify responsive behavior
  - Time the presentation (should be 10-12 minutes)
  - **Files:** `presentations/pair-chat-presentation.html`
  - **Effort:** 20 minutes
  - **Dependencies:** Task 3.1 complete

- [ ] **Task 3.3: Run diagnostics and build checks**
  - Run lsp_diagnostics at project level
  - Verify no errors introduced
  - **Effort:** 5 minutes
  - **Dependencies:** All tasks complete

---

## Execution Strategy

**Sequential execution required** - tasks build on each other.

**Order:**
1. Task 1.1 (restructure markdown)
2. Task 1.2 (update HTML structure)
3. Task 2.1 (split dense markdown slides)
4. Task 2.2 (implement visual hierarchy in HTML)
5. Task 3.1 (verify sync)
6. Task 3.2 (test delivery)
7. Task 3.3 (diagnostics)

**Estimated total time:** 7-10 hours

---

## Notes

- This is a presentation refactor, not code changes
- No build/test commands needed (static HTML)
- Focus on content clarity and visual impact
- User preference: simpler, more direct narrative while maintaining strategic depth
