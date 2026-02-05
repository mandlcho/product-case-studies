# HAS (Health Appointment System): Prevention Through Frictionless UX at Scale

**Product**: Health Appointment System (HAS)  
**Organization**: Open Government Products (OGP), Singapore  
**Domain**: Preventive care, vaccination, screening bookings  
**Launch**: 2022  
**Status**: Active, expanding  
**Public Report Card**: reports.open.gov.sg/has

---

## Executive Summary

Health Appointment System (HAS) shifted Singapore's healthcare system from **reactive to proactive** by making preventive care frictionless. Citizens see exactly which vaccines and screenings they're due for, book with one click, and receive clinic-initiated outreach reminders. The platform now handles **100k+ appointments per quarter** across two-thirds of CHAS GP clinics island-wide.

**Core insight**: Prevention requires three elements—**visibility** (what am I due for?), **accessibility** (can I easily book?), and **activation** (do I get reminded?). HAS engineered all three.

---

## The Problem: Reactive Healthcare System

### The Baseline
Before HAS, Singapore's vaccination and screening landscape was episodic:
- **Citizens didn't know what they were due for** – No central visibility into recommended vaccines/screenings by age, sex, medical history
- **Booking required manual coordination** – Call the clinic, check if slots available, navigate multiple systems
- **Outreach was passive** – Healthcare leaflets and posters weren't reaching people who needed them most
- **No funnel visibility** – Ministry of Health (MOH) and Health Promotion Board (HPB) couldn't measure campaign effectiveness

### The Health System Goal
Singapore's "Healthier SG" initiative aimed to **shift from episodic (I'm sick, I call a doctor) to preventive (I know what's due for me)**. But achieving this required removing friction from the patient journey.

### The Friction Points
1. **Information asymmetry**: Citizens didn't know national vaccination schedules
2. **Booking friction**: Multiple systems, multiple calls, multiple wait times
3. **Provider coordination**: GPs couldn't proactively outreach to their patient panels
4. **Measurement blind spot**: No centralized data on campaign reach or uptake

---

## The Solution: Visibility + Accessibility + Activation

### 1. Eligibility as a UX Feature

**The Insight**: Most health tech assumes users already know what they need. HAS flipped this—**show users what they're due for before asking them to book**.

#### How It Works
- **Input**: Citizen's age, sex, and medical record data (pulled from National Immunisation Registry + EMRs)
- **Logic**: Eligibility rules matching national vaccination/screening schedules
- **Output**: Personalized list of "You're due for..." (HPV vaccine, pneumococcal booster, mammogram, etc.)

#### Impact
Citizens see actionable, personalized guidance instead of generic health messaging. This solves the "I didn't know I needed this" problem—a major blocker to preventive care.

### 2. Unified Booking Interface

HAS consolidates multiple preventive services into one platform:

| Service Category | Examples | Integration |
|------------------|----------|-------------|
| **Vaccinations** | HPV, pneumococcal, flu, COVID, childhood vaccines | National Adult Immunisation Schedule (NAIS) |
| **Screenings** | Mammograms, ultrasound, X-ray, lab tests | Screen for Life program, NHG polyclinics |
| **Preventive Consultations** | Healthier SG wellness checks | HealthHub, Healthier SG CRM |

**Before**: A 55-year-old woman had to navigate 3+ different booking systems (cervical screening → mammogram → blood tests).  
**After**: One platform shows all due services; one booking interface; one confirmation.

### 3. GP Clinic Admin Portal

Clinics needed tools to manage demand and reach their patient panels:

**Features**:
- Slot management (open/close dates per service, partial day closures, custom durations)
- Healthier SG enrollee outreach (see who enrolled, who's been contacted)
- Real-time queue management (reduce walk-in congestion)
- CSV analytics exports (understand clinic-level demand patterns)
- Bulk clinic-initiated bookings (proactively invite patients due for services)

**Impact**: GPs aligned their business operations with preventive health goals. They could now **actively manage their patient panels** rather than passively responding to demand.

### 4. Discovery & Accessibility

**Google Maps Integration**:
- HAS booking links embedded on CHAS clinic Google Business Profiles
- Reduces discovery friction for patients searching "vaccine near me"

**Multilingual Interface**:
- Support for English, Chinese, Malay, Tamil
- Removes language as barrier to preventive care

**SMS Campaigns** (2024–2025):
- Automated outreach to populations with low uptake
- Example: SMS to all women aged 18–45: "You're due for HPV vaccine. Book at [link]"
- Example: SMS to seniors: "Pneumococcal booster recommended. [4 available clinics]"

---

## Product Evolution: Crisis → Peacetime

### Phase 1: COVID-19 Vaccination (2020–2021)
**The Crisis**: Singapore needed to vaccinate millions in weeks. OGP built a **COVID-19 Vaccination National Appointment System** in ~2 weeks.

**Scale**: Administered 13M+ vaccine doses through the system during pandemic peak.

### Phase 2: Generalization to HAS (2022–2023)
**The Insight**: The appointment booking infrastructure built for COVID was **generalizable to all preventive care**.

In 2023, OGP **merged the COVID vaccination system into HAS** and expanded it to include:
- All vaccines in National Adult Immunisation Schedule
- Healthier SG consultations
- Screen for Life diagnostics
- HPV, pneumococcal, flu campaigns

### Phase 3: Sustained Capability (2024–2025)
Rather than letting crisis infrastructure lapse, OGP:
- Built **vaccine.gov.sg** as public education layer (what vaccines do you need?)
- Launched **clinic-initiated booking campaigns** (GPs invite patients)
- Created **HealthierSGEventsGoWhere** directory (link preventive appointments to lifestyle programs)

**Implication**: Crisis-driven tech that's thoughtfully maintained becomes institutional capability.

---

## Architecture & Technical Approach

### Data Integrations

```
┌─────────────────────────────────────────────┐
│          HAS (Unified UX)                   │
│  ┌──────────────────────────────────────┐   │
│  │  Eligibility Engine                  │   │
│  │  - Check who's due for what          │   │
│  │  - Personalization rules             │   │
│  └──────────────────────────────────────┘   │
└──────────────────┬──────────────────────────┘
                   │
     ┌─────────────┼─────────────┐
     │             │             │
     v             v             v
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│   National   │ │    EMR       │ │  HealthHub / │
│ Immunisation │ │   Systems    │ │  Healthier   │
│   Registry   │ │              │ │    SG CRM    │
│    (NIR)     │ │              │ │              │
└──────────────┘ └──────────────┘ └──────────────┘
```

**Data Flow**:
1. **Eligibility check**: NIR + EMRs → Is this person due for vaccination X?
2. **Slot availability**: GP clinic portals → What dates/times are open?
3. **Booking confirmation**: SMS + HealthHub → Appointment scheduled
4. **Analytics**: HAS backend → Uptake metrics, coverage by clinic

### Key Features by Timeline

| Year | Feature | Impact |
|------|---------|--------|
| **2022–2023** | Launch at CHAS GPs; Healthier SG integration; Queue management | Foundational booking infrastructure |
| **2023** | NIR integration; flu campaigns; multilingual UX | Personalization at scale |
| **2024** | Vaccine Advisor (AI decision support for doctors); vaccine.gov.sg | Clinical support + public education |
| **2024–2025** | Automated SMS campaigns; clinic-initiated bookings; Business Profile integration | Activation & outreach at scale |

---

## Measurement & Impact

### Quantified Metrics

**Scale**:
- **100k+ completed appointments per quarter** (Q4 2024 – Q1 2025)
- **Approaching 2/3 coverage** of CHAS GP clinics island-wide
- **13M+ vaccine doses** administered through predecessor system (COVID era)

**User Satisfaction**:
- **Strong Net Promoter Scores** from both public users and clinic staff
- Positive feedback on eligibility visibility and booking simplicity

**Campaign Effectiveness**:
- **HPV uptake**: Measurable improvements in young women reaching clinics
- **Pneumococcal uptake**: Measurable improvements in seniors
- **Flu campaigns**: Seasonal variation tracking

### Operational Insights

**System Shift**:
- From: "Why should I get vaccinated?" (needs education)
- To: "I know I need this, I can book in 2 clicks" (removes friction)

**Clinic Operations**:
- GPs can now **measure and manage** their preventive care performance
- Slot utilization data informs staffing and outreach
- Proactive outreach shifts from passive to active patient management

---

## Product Decisions & Design Thinking

### Decision 1: Eligibility as Primary Feature (Not Secondary)

Most healthcare booking systems assume users know what they need. HAS inverted this:
- **Show first**: "You're due for HPV vaccine"
- **Ask second**: "When would you like to book?"

This single decision dramatically reduced booking friction and improved uptake.

### Decision 2: Unified Interface Over Federated Systems

Option A (federated): Separate booking for vaccines, screening, consultations (like pre-HAS)  
Option B (unified): Single platform, one user journey

**HAS chose unified** because:
- Citizens see all preventive services in one place
- Clinics manage demand centrally
- Ministry can measure system-wide coverage

### Decision 3: Clinic-Initiated Outreach at Scale

Rather than expecting patients to proactively book, HAS enables **clinic-initiated campaigns**:
- GPs can target specific populations ("All unvaccinated 50+ year-olds")
- SMS reminders with clinic availability
- Data-driven outreach (see who's overdue, who's high-risk)

**Impact**: Converts passive "here's what's available" to active "you need this".

### Decision 4: Privacy-First Data Integration

HAS pulls medical eligibility from NIR and EMRs, but:
- Citizens see **what's due for them**, not raw medical data
- Eligibility rules are **transparent** (national health guidelines, not black-box algorithms)
- Data stays within government infrastructure (no third-party APIs)

---

## Lessons for Product Leaders

### 1. **Visibility Reduces Friction More Than Anything Else**

Prevention doesn't require exotic technology. It requires:
- **Show me what I'm due for** (eligibility)
- **Let me easily book it** (frictionless UX)
- **Remind me to do it** (activation)

HAS nailed all three. This is true in healthcare, but also in B2B, finance, and anywhere people delay what they know they should do.

### 2. **Provider Tooling Matters as Much as Patient UX**

HAS could have been just a citizen-facing booking app. But **clinic admin portals** were equally important:
- GPs needed to manage slots and see their Healthier SG panels
- Without provider alignment, patient features don't get used

**Implication**: In healthcare (and regulated sectors), design for the entire ecosystem, not just end users.

### 3. **Measurement Enables Behavior Change**

Before HAS, HPB couldn't answer: "What fraction of eligible people got HPV vaccines this quarter?"

Now they can see:
- Campaign reach (how many SMS sent)
- Conversion (how many booked)
- Outcome (how many doses administered)

**Implication**: Public measurement creates accountability and enables continuous improvement.

### 4. **Crisis Infrastructure Can Become Core Capability**

HAS emerged from COVID-19 vaccination infrastructure. Rather than sunsetting it, OGP:
- Generalized the booking model
- Integrated with other preventive services
- Built sustained tooling (vaccine.gov.sg, clinic dashboards)

**Implication**: When crisis-born tech solves a real problem, invest in long-term sustainability.

### 5. **Preventive Care Requires System Redesign, Not Just UX**

HAS is a UX/product story, but the real change is **system-level**:
- GPs now have incentives to manage preventive care panels
- Ministry has visibility into preventive care coverage
- Citizens see preventive care as "things I'm due for" not "optional health tips"

**Implication**: The hardest part isn't building the product; it's aligning incentives across the ecosystem.

---

## Competitive Context

### Why HAS Works When Others Don't

Other countries have built vaccination booking systems. Why is HAS notable?

| Aspect | HAS | Typical Systems |
|--------|-----|-----------------|
| **Eligibility** | Personalized (based on age, sex, medical history) | Generic ("Book vaccine here") |
| **Scope** | Unified (vaccines + screening + consultations) | Siloed (separate systems) |
| **Provider Tools** | Clinic admin portal, panel management, outreach | Bare minimum slot management |
| **Outreach** | Clinic-initiated SMS campaigns | Passive (list available services) |
| **Measurement** | Public report card with detailed metrics | Often opaque |
| **Integration** | NIR + EMRs + HealthHub + vaccine.gov.sg | Point-to-point connections |

---

## Real-World Impact: Three Stories

### Story 1: The Busy Professional
**Before HAS**: 42-year-old woman hasn't had mammogram in 3 years. Doesn't know she's eligible for Healthier SG screening. Would need to call clinic, wait on hold, check personal calendar.

**With HAS**: App shows "You're due for mammogram and HPV screening." She books both in 2 minutes, gets SMS reminder week before. Attends both appointments.

**Impact**: Shifted from "I'm too busy" to "I'm taken care of."

### Story 2: The Clinic Manager
**Before HAS**: Clinic manager manages slots manually, no data on which services patients want. Can't tell which patients are overdue.

**With HAS**: Dashboard shows "50 seniors overdue for pneumococcal." Manager sends bulk SMS campaign. Sees 40% conversion to bookings. Staffs accordingly.

**Impact**: Clinic capacity planning becomes data-driven.

### Story 3: The Public Health Officer
**Before HAS**: HPB runs HPV campaign. Doesn't know reach ("How many eligible women saw our ads?"). No data on uptake by region.

**With HAS**: Campaign SMS sent to 200k eligible women. Sees 35% click-through rate, 20% conversion to booking. Can iterate on messaging for underperforming regions.

**Impact**: Public health campaigns become measurable and optimizable.

---

## Challenges & Open Questions

### Challenge 1: Clinic Adoption
Two-thirds of CHAS clinics use HAS, but not all. Why?
- Training burden on clinic staff
- Workflow change resistance
- Small clinics may not see ROI from admin portal

**OGP's approach**: Continued training, simplified UX, phased rollout.

### Challenge 2: Data Freshness
Eligibility depends on timely data from NIR and EMRs. What if data is stale?
- A person who recently had a vaccine might still see it as "due"
- Inconsistency between HAS and clinic records

**OGP's approach**: Regular syncs with upstream systems, conflict resolution workflows.

### Challenge 3: Equity in Digital Access
HAS is digital-first. What about populations without smartphones?
- Older adults, lower-income groups may face barriers
- SMS outreach helps, but requires phone number and basic literacy

**OGP's approach**: SMS as primary channel (lower friction than app), clinic staff can help book, paper forms still available.

### Challenge 4: What's the Outcome?
HAS measures appointments booked, but does it actually improve health outcomes?
- Vaccination rates went up, but were they sustainable?
- Did preventive appointments lead to earlier disease detection?

**OGP's approach**: Public report cards publish metrics (incomplete data, but transparent).

---

## Future Roadmap (Inferred)

Based on current trajectory, HAS likely to evolve toward:

### Phase 1 (Current): Vaccination + Screening + Consultation
- Expand clinic coverage (remaining 1/3 of CHAS clinics)
- Refine outreach campaigns by population segment

### Phase 2 (Likely): Integration with Downstream Care
- Link preventive appointments to chronic disease management
- If person books wellness check, offer diabetes screening if at-risk
- Create care pathways from prevention → early detection → treatment

### Phase 3 (Possible): Predictive Outreach
- AI models to identify high-risk populations
- Proactive outreach to people likely to benefit most from screening
- Example: "Based on your risk factors, pneumococcal vaccine recommended"

### Phase 4 (Speculative): Lifestyle Integration
- Link vaccine.gov.sg to HealthierSGEventsGoWhere (join fitness class with vaccination)
- Gamification (badges for hitting preventive health milestones)
- Integration with wearables (activity data → fitness recommendations)

---

## Why This Matters: Prevention Economics

### The System Cost of Prevention Failure

One person missing preventive care might cost the health system:
- $5k – $15k per late-stage cancer diagnosis
- $2k – $5k per preventable hospitalization
- Years of productivity loss to patient and employer

### The Efficiency of Prevention

HAS's incremental cost:
- Appointment system: ~$10–50 per person per year
- SMS outreach: ~$0.01–0.05 per message
- Staff time: Minimal (largely automated)

**ROI**: If HAS prevents even 1% of preventable hospitalizations in its catchment, it pays for itself many times over.

---

## Teardown Summary

| Dimension | Insight |
|-----------|---------|
| **Core Problem** | Preventive care is episodic and reactive; people don't know what they're due for |
| **Key Innovation** | Eligibility visibility + unified booking + clinic outreach = prevention at scale |
| **User Impact** | Citizens see exactly what they're due for; book in 2 clicks; get reminded |
| **Provider Impact** | Clinics can manage preventive care panels, measure outcomes, align with health goals |
| **System Impact** | Ministry can measure preventive care coverage, run data-driven campaigns, shift culture |
| **Measurement** | 100k+ appointments/quarter, 2/3 clinic coverage, strong NPS, measurable campaign lift |
| **Replicability** | Pattern (eligibility + unified booking + outreach) works across healthcare, wellness, gov services |

---

## Quotes & Sources

> "Shifts the system from episodic to preventive care by making recommended vaccines and screenings easier to discover and book."  
> — OGP healthcare findings

> "Most of the changes start with a process change. Then HAS just enables it."  
> — Paraphrase of OGP philosophy (applies across their health products)

**Public Report Card**: https://reports.open.gov.sg/has  
**Booking Portal**: https://book.health.gov.sg  
**Education Layer**: https://vaccine.gov.sg

---

## Next Steps for Organizations

If you're building preventive care platforms:

1. **Start with eligibility visibility** – Don't assume users know what they need
2. **Unify the interface** – Don't force users to navigate multiple systems
3. **Design for providers, not just patients** – Clinic tools are as important as citizen UX
4. **Measure everything** – Public transparency drives accountability and continuous improvement
5. **Think ecosystem** – Integrate with education (vaccine.gov.sg), lifestyle (Active SG), data (NIR, EMRs)

If you're in healthcare policy:

1. **Prevention requires infrastructure** – Not just messaging; make it easy to actually book
2. **Provider alignment matters** – Give GPs tools to manage their preventive care outcomes
3. **Measurement creates change** – Public metrics drive behavior more than policy
4. **Crisis tech can go mainstream** – Don't let good crisis-born infrastructure lapse

---

**Case Study by**: Claude Code  
**Based on**: OGP research (ogp-healthcare.md, ogp-healthcare-findings.md)  
**Last Updated**: February 2025
