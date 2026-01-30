# Pair Chat: Product Introduction Presentation
## OGP Senior Product Manager Interview

**Prepared by:** Mandl Cho  
**Date:** January 30, 2026  
**Duration:** 8-10 minutes

---

## 1. THE HOOK (30 seconds)

[SPEAKER NOTE: Open with confidence. Pause after the hook for impact.]

**"20,000 custom AIBots created by users in 18 months."**

That's not a feature adoption metric—that's a platform signal. Pair Chat has crossed the threshold from **tool** to **platform**. Users aren't just consuming AI assistance; they're creating institutional knowledge at scale.

But here's the tension: **Only 70% of public officers are using it.** The remaining 30%—roughly 45,000 officers—represent untapped potential worth an estimated **$8.7M in monthly productivity gains**.

The question isn't "Does Pair Chat work?" It's **"How do we capture the value we're leaving on the table?"**

---

## 2. CONTEXT: Understanding Pair Chat (1 minute)

[SPEAKER NOTE: Establish product fluency. Weave metrics into narrative, don't list them.]

Pair Chat is Singapore's government-specific AI assistant—think ChatGPT, but **cleared for RESTRICTED/SENSITIVE NORMAL data** and **zero-cost** to all 150,000 public officers.

**The numbers tell a compelling story:**

- **78,517 monthly active users** (70% of public service)
- **832,280 hours saved monthly** (59 minutes per task on average)
- **$28.9M in estimated monthly savings** vs. $450K development cost
- **4.2/5 user satisfaction** rating

But the most revealing metric is this: **149,000 registered users, but only 78,517 active.** That's a **47% activation gap**—70,000 people signed up but aren't using it regularly.

**What Pair Chat does:**
- Secure chat interface (like ChatGPT, but gov-cleared)
- Custom Assistants (20,000+ created by users)
- Specialized tools: Pair Search (legislative research), Pair Noms (meeting minutes), Batch Jobs (bulk analysis)

---

## 3. THE INSIGHT: From Tool to Platform (2-3 minutes)

[SPEAKER NOTE: This is your original POV. Speak with conviction.]

### The Pattern I See

Most product teams would look at 70% adoption and celebrate. I see **three interconnected signals** that reveal a deeper opportunity:

**Signal 1: The 20,000 AIBot Explosion**
- Users aren't just using Pair Chat—they're **building on it**
- Examples: SGH's "Proph Abby" (antibiotic prescriptions), BCA's compliance reviewers, PA's Charity Act interpreter
- This is **bottom-up innovation** at scale

**Signal 2: The Activation Gap**
- 149K registered, 78.5K active = **47% aren't converting**
- These aren't people who tried and left—they signed up but never started
- Classic **trust + discoverability problem**, not a capability problem

**Signal 3: The Case Study Pattern**
- SGH: 95% compliance (up from 80%), 90% time savings
- BCA: "Hours to minutes" for report reviews
- PA: Self-service enabled for complex legislation

**What these three signals mean together:**

When users **trust** Pair Chat enough to use it, they don't just use it—they **build institutional knowledge** with it. The 20,000 AIBots aren't just productivity hacks; they're **codified expertise** that compounds over time.

### The Core Problem

**Pair Chat has solved the "create value" problem. The challenge now is the "capture value" problem.**

Specifically:
1. **Trust barrier:** 30% of officers don't trust it enough to start (security concerns, hallucination fears, unclear safe-use boundaries)
2. **Discoverability gap:** Officers who would benefit don't know which use cases fit their work
3. **Quality variance:** 20,000 user-created AIBots with no governance = inconsistent quality and potential risk

**This isn't a feature gap—it's a platform maturity problem.**

---

## 4. IMPLICATION: What This Means for Product Strategy (2 minutes)

[SPEAKER NOTE: Show strategic thinking. Discuss trade-offs explicitly.]

### The Strategic Choice

If Pair Chat is becoming a platform, we face a classic platform dilemma:

**Option A: Expand the user base** (focus on the 30% non-users)
- Pros: Unlock $8.7M/month in potential savings, broader impact
- Cons: Requires trust-building, change management, onboarding at scale

**Option B: Deepen engagement** (focus on the 70% active users)
- Pros: Compound value through better AIBots, network effects, institutional knowledge
- Cons: Leaves 45,000 officers on the table, limited growth ceiling

**Option C: Platform governance** (focus on the 20,000 AIBots)
- Pros: Quality control, risk mitigation, enable sharing/discovery
- Cons: Could slow innovation, requires new capabilities (curation, evaluation)

### My Recommendation: **Option A + C in sequence**

**Why:**
1. The 47% activation gap is **low-hanging fruit**—these people already signed up
2. Platform governance (Option C) is **table stakes** as AIBots proliferate
3. Deepening engagement (Option B) happens naturally once trust + governance are solved

**Trade-off I'm making:**
- **Deprioritizing:** New features, model upgrades, expanding to new use cases
- **Prioritizing:** Trust-building UX, onboarding, AIBot quality/discovery

**Why this trade-off makes sense:**
- Pair Chat already has strong capabilities (Claude Sonnet 4, document uploads, batch jobs)
- The bottleneck isn't "what it can do"—it's "who trusts it" and "how to find the right AIBot"

---

## 5. PATH FORWARD: 30/60/90 Day Plan (2 minutes)

[SPEAKER NOTE: Be specific. Show you can execute, not just strategize.]

### Focus Area: **Closing the Activation Gap**

**Goal:** Convert 20% of inactive registered users (14,000 officers) to monthly actives within 90 days

**Success Metrics:**
- MAU increase from 78.5K → 92.5K
- Activation rate from 53% → 62%
- "First meaningful task completed" within 7 days of first login

---

### 30 Days: **Make Trust Visible**

**Problem:** Officers don't trust Pair Chat because they don't understand the safety model

**Actions:**
1. **In-product trust signals:**
   - Add persistent "What's safe to share" banner on first 3 sessions
   - Show "Your data is not logged by LLM providers" on every chat start
   - Create "Safe Use Checklist" for high-risk tasks (policy drafting, public comms)

2. **Instrument the trust gap:**
   - Add lightweight survey: "What's stopping you from using Pair Chat more?" (3 options, 1-click)
   - Track: % of users who see trust messaging vs. complete first task

3. **Quick win: Onboarding templates**
   - Create 5 persona-based starter prompts (policy officer, ops, comms, analytics, HR)
   - Example: "Draft a meeting agenda for a cross-agency working group"
   - Reduces "blank page" problem

**Effort:** 2 weeks (design + eng), 2 weeks (rollout + measure)

**Risk:** Trust messaging could backfire if it highlights risks users hadn't considered
- **Mitigation:** A/B test messaging with 10% of inactive users first

---

### 60 Days: **Make Discovery Effortless**

**Problem:** Officers don't know which AIBots exist or which ones are high-quality

**Actions:**
1. **AIBot marketplace (MVP):**
   - Curated directory of top 50 AIBots by use case (procurement, HR, compliance, research)
   - Show: Creator, use case, # of users, avg rating
   - Filter by: Agency, function, task type

2. **Quality signals:**
   - Add "Verified" badge for AIBots tested by Pair team (using Pair Rome evaluation suite)
   - Show usage stats: "Used by 200+ officers across 15 agencies"

3. **Personalized recommendations:**
   - On login: "Officers in your agency are using these AIBots" (3 suggestions)
   - Based on: Agency, job function (from Azure AD), similar user behavior

**Effort:** 4 weeks (build marketplace), 2 weeks (curate + verify top 50)

**Risk:** Curation creates bottleneck; users expect all 20,000 AIBots to be verified
- **Mitigation:** Start with top 50, add "Community" tab for unverified AIBots with disclaimer

---

### 90 Days: **Make Adoption Compounding**

**Problem:** Individual adoption doesn't spread to teams

**Actions:**
1. **Team-level visibility (without surveillance):**
   - Agency dashboard: "Top 10 AIBots used in your agency" (aggregated, anonymized)
   - "Common prompts" library: Shareable templates from high-performing users

2. **Onboarding kits by agency:**
   - Partner with 5 agencies with low adoption (<50%)
   - Create agency-specific starter packs: "Top 5 AIBots for [Agency Name]"
   - Run 30-min "Pair Chat Office Hours" (live demo + Q&A)

3. **Measure compounding:**
   - Track: % of new users who discover Pair via colleague recommendation
   - Track: % of AIBots that are shared across teams (vs. individual use)

**Effort:** 3 weeks (build dashboards), 3 weeks (agency partnerships + onboarding)

**Risk:** Agencies may resist "visibility" as surveillance
- **Mitigation:** Make dashboards opt-in for agencies; emphasize "learning" not "monitoring"

---

### What I'm NOT Doing (and Why)

**Not doing:**
- ❌ New features (e.g., Pair Scribe, new integrations)
- ❌ Model upgrades (Claude Sonnet 4 is already strong)
- ❌ Expanding to citizen-facing use cases

**Why:**
- The bottleneck is **adoption**, not **capability**
- New features add complexity before we've nailed the core loop
- Focus beats breadth in the next 90 days

**When I'd revisit:**
- If activation rate hits 70%+ (trust problem solved)
- If AIBot marketplace shows clear demand for specific missing capabilities
- If case studies reveal capability gaps (not seeing this in SGH/BCA/PA data)

---

## 6. CLOSE: The One Thing That Matters (30 seconds)

[SPEAKER NOTE: End with conviction. No hedging.]

**The one thing I'd bet on: Trust is the unlock.**

Pair Chat has proven it can create value—832,280 hours saved monthly, 20,000 AIBots, 95% compliance rates in healthcare. The next phase isn't about building more—it's about **making what exists trustworthy, discoverable, and shareable**.

If we close the activation gap, we don't just add 14,000 users. We unlock **network effects**: more AIBots, more shared knowledge, more compounding value.

**That's the platform play.**

---

## APPENDIX: Backup Slides (If Time Permits)

### Competitive Positioning

| Dimension | Pair Chat | ChatGPT |
|-----------|-----------|---------|
| **Data Classification** | RESTRICTED/SENSITIVE NORMAL | Public only |
| **Cost** | Free | $20/month |
| **Logging** | No LLM provider logging | Logged for training |
| **Context** | Singapore gov-specific | General purpose |
| **Integration** | Azure AD, GSIB devices | Public access |

**Moats:**
1. **Regulatory:** Government data clearance (commercial tools can't match)
2. **Network effects:** 20,000 AIBots create institutional knowledge
3. **Integration:** Deep gov system integration (Azure AD, GSIB)
4. **Trust:** Rigorous evaluation (Pair Rome suite)

---

### Key Metrics Summary

| Metric | Value | Insight |
|--------|-------|---------|
| **MAU** | 78,517 | 70% of public service |
| **Registered Users** | 149,000 | 47% activation gap |
| **Hours Saved/Month** | 832,280 | 59 min/task avg |
| **Monthly Savings** | $28.9M | vs. $450K dev cost |
| **AIBots Created** | 20,000+ | Platform signal |
| **User Satisfaction** | 4.2/5 | Strong product-market fit |

---

### Questions This Raises

1. **How do we measure the $28.9M savings claim?** (Self-reported? Validated?)
2. **What's the quality distribution of 20,000 AIBots?** (Top 10% vs. bottom 10%?)
3. **Why did 70,000 people register but not activate?** (Need user research)
4. **What's the retention curve?** (D1, D7, D30 retention rates?)
5. **How do we prevent AIBot sprawl?** (Governance model?)

---

## Sources

**Internal Research:**
- Pair Chat teardown (2026-01-27)
- Public sentiment analysis (2026-01-27)

**External Sources:**
- [pair.gov.sg](https://pair.gov.sg) (Official product site)
- [reports.open.gov.sg/pair](https://reports.open.gov.sg/pair) (Report cards, Q3 2025)
- [developer.tech.gov.sg](https://www.developer.tech.gov.sg/products/categories/productivity-tools/pair) (Developer portal)
- Straits Times coverage (2023-2025)
- UNDP Policy Centre blog (Sept 2024)
- MDDI Parliamentary responses (Nov 2025)

---

**END OF PRESENTATION**

[SPEAKER NOTE: Total time: ~8-10 minutes. Practice out loud to calibrate pacing. Be ready to skip Appendix if time is tight.]
