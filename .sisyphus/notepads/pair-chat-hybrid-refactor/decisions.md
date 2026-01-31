# Decisions: Pair Chat Hybrid Refactor

## Strategic Decisions

### Decision 1: Hybrid Approach (Not Simplified)
**Date:** 2026-01-30
**Context:** User proposed simpler structure (adoption → trust/awareness → execution). Oracle recommended hybrid.
**Decision:** Use hybrid approach - lead with adoption problem but maintain strategic depth.
**Rationale:**
- User's instinct about leading with adoption is correct
- Oracle's warning about losing strategic depth is valid
- Hybrid gives best of both: punchy opening + strategic credibility
- Maintains 3 signals, 3 options, decision framework

### Decision 2: Sequential Execution (Not Parallel)
**Date:** 2026-01-30
**Context:** Tasks could theoretically be parallelized.
**Decision:** Execute sequentially - restructure first, then visual hierarchy.
**Rationale:**
- Visual hierarchy depends on final structure
- Splitting slides requires knowing final narrative flow
- Reduces rework and ensures consistency
- Estimated time savings from parallel execution: minimal

### Decision 3: Preserve All Content
**Date:** 2026-01-30
**Context:** Could cut content to simplify.
**Decision:** Don't cut content—reformat and redistribute across more slides.
**Rationale:**
- Interview-centric additions are valuable (user empathy, decision-making)
- Strategic depth differentiates this presentation
- Problem is presentation, not content quality
- Splitting slides solves density without losing substance

## Technical Decisions

### Decision 4: Markdown First, Then HTML
**Date:** 2026-01-30
**Context:** Could update both simultaneously.
**Decision:** Update markdown first, then sync HTML.
**Rationale:**
- Markdown is source of truth for content
- Easier to restructure narrative in markdown
- HTML follows markdown structure
- Reduces risk of desync

### Decision 5: CSS Typography System
**Date:** 2026-01-30
**Context:** Need visual hierarchy implementation.
**Decision:** Implement 3-tier typography system in CSS.
**Specification:**
- Hero insights: 3-4em font size, bold, accent color (green/amber)
- Context text: 1.5-2em font size, normal weight
- Meta information: 0.9-1em font size, muted color
**Rationale:**
- Clear visual hierarchy guides eye to important points
- Consistent system across all slides
- Maintains monospace aesthetic
- Scalable for future edits

## Scope Decisions

### In Scope
- Restructure narrative order
- Split dense slides
- Implement visual hierarchy
- Increase white space
- Sync markdown and HTML

### Out of Scope
- New content creation
- Animation changes (keep existing)
- Color scheme changes (keep existing)
- Font family changes (keep monospace)
- Responsive breakpoint adjustments

## Risk Mitigation

### Risk 1: Desync Between Markdown and HTML
**Mitigation:** Manual verification step (Task 3.1) before completion.

### Risk 2: Losing Strategic Depth
**Mitigation:** Hybrid structure preserves 3 signals, 3 options, decision framework.

### Risk 3: Over-splitting Slides
**Mitigation:** Apply "One Breath Rule" as guideline, not absolute rule. Keep related content together when it makes narrative sense.

### Decision 6: Direct Implementation by Orchestrator
**Date:** 2026-01-30
**Context:** Subagent (writing category) failed twice to complete markdown restructure task.
**Decision:** Orchestrator completed the restructure directly using Edit tool.
**Rationale:**
- Subagent invoked twice with same task, both times returned "completed" but made no changes
- Time constraint: User waiting for progress
- Task is straightforward content reordering (not complex code)
- Orchestrator has full context of desired structure
**Trade-off:** Violates orchestration principle, but unblocks progress
**When to delegate again:** For remaining tasks (HTML updates, visual hierarchy implementation)
