# Healthcare Case Study Angles: OGP Deep Dive

**Date**: February 2025  
**Source**: OGP healthcare research (ogp-healthcare.md, ogp-healthcare-findings.md)  
**Purpose**: Identify and develop strongest teardown/case study candidates from OGP's healthcare portfolio

---

## Executive Summary

OGP's healthcare portfolio offers **5 tier-1 case study candidates**, each with distinct angles and audiences:

1. **Bright** – Process-First Product Strategy (Highest potential)
2. **Care360** – Social-Care as Critical Infrastructure
3. **HAS** – Prevention Through Frictionless UX at Scale
4. **Rooster** – High-Stakes Alerting & Operational Safety
5. **Scribe** – On-Prem AI in Regulated Environments

Each could become a standalone teardown or be bundled into thematic clusters (e.g., "Process Design in Healthcare", "AI in Public Sector", "Interoperability as Coordination").

---

## Tier 1: Highest-Potential Case Studies

### 1. **BRIGHT: "Process Change as Product Strategy"**

#### The Story
Referral bottlenecks delayed hospital discharge and community placement by 3–8 weeks. Rather than rushing to build software, OGP redesigned workflows first. Bright emerged as an enabler, not the driver.

#### Key Angles
- **Process-First Design Philosophy**
  - Deep stakeholder mapping (hospitals, ILTC providers, patients)
  - Workflow redesign before tech design
  - Quote: "Most of the changes on Bright start with a process change. Then Bright just enables it."
  
- **Referral Bottleneck as Leverage Point**
  - Each delayed referral cascades (hospital bed occupied, patient can't discharge, ILTC provider loses capacity)
  - Small friction reduction = massive system-level impact
  - Operationally quantifiable (weeks → days)

- **Multi-Stakeholder Collaboration Model**
  - Unified workspace for hospitals, ILTC providers, social workers
  - Service matching by region, care needs, availability
  - Bed-level vacancy management (different models for nursing homes vs. hospice)

- **Scalable Rollout Strategy**
  - Phase 1: All nursing home referrals transitioned
  - Phases 2–4: 14 additional referral forms (daycare, home care, community mental health)
  - 5,000+ healthcare professionals trained
  - Phased approach reduced risk and allowed continuous learning

#### Why It's a Strong Case Study
- **Universal appeal**: Process redesign methodology applies to healthcare, gov, enterprise
- **Measurable impact**: Reduced referral delays (weeks → days); faster hospital discharge
- **Clear narrative**: Problem → Process Redesign → Technology → Rollout
- **Thought leadership**: Challenges tech-first mentality; shows when to slow down

#### Teardown Structure
1. **The Problem** – Referral delays cascading through system
2. **The Process Discovery** – How OGP mapped workflows and identified friction
3. **The Redesign** – What changed in how referrals flow
4. **The Technology** – How Bright enables new workflows (not the reverse)
5. **The Rollout** – Phased approach to adoption
6. **The Impact** – Measurable operational improvements

#### Who Should Care
- Healthcare system leaders implementing digital transformation
- Product managers in regulated environments (finance, gov, healthcare)
- Process designers / operational excellence teams

#### Key Metrics to Feature
- 5,000+ healthcare professionals trained
- Phased rollout across 5+ referral types
- Reduced referral processing time (weeks → days)
- Active in all major healthcare clusters (SingHealth, NHG, NUHS)

---

### 2. **CARE360: "Social-Care as Clinically Critical Infrastructure"**

#### The Story
Medical social workers (MSWs) were re-collecting patient information (financial hardship, social issues) across institutions because systems didn't talk to each other. Care360 centralized patient context, enabling holistic care coordination across the entire public healthcare system.

#### Key Angles
- **Interoperability as Coordination Mechanism**
  - Unified patient profile pulling data from 6+ EMRs + government sources (DataHive)
  - MSWs no longer lose patient context when patients move across institutions
  - Eliminates traumatic repetitive history-taking ("Tell me again why you can't afford medication...")

- **System Replacement at Scale**
  - Replaced legacy system (NeMSW) across entire public healthcare system
  - Rollout scope: 12 SingHealth PHIs + 6 NHG PHIs + 2 additional NHG PHIs + 6 NUHS PHIs + 4 VWO community hospitals
  - Complete migration completed 2023–2025
  - Integrated with 6+ downstream systems (NGEMR, Sunrise, NeFR, MFEC, SSNet)

- **AI Integration as Secondary Feature (Scribe)**
  - Initial: Embedded AI transcription in Care360
  - Evolution: Standalone Scribe platform for broader healthcare workers
  - Feature: LLM-powered Care360 summaries (2025) for quick case context
  - Demonstrates how AI enhances rather than replaces domain expertise

- **Social Care as Equal to Clinical Care**
  - Financial assistance workflows now digital (vs. paper forms)
  - Faster approvals for straightforward cases
  - Operational visibility dashboards for critical cases
  - Audit logs and compliance tracking

- **Data Governance in Motion**
  - Consent-based data sharing across institutions
  - Sensitive financial/social data across org boundaries
  - Clear audit trails for accountability

#### Why It's a Strong Case Study
- **Broadens the definition of "health tech"**: Social care, not just clinical
- **System replacement story**: How to migrate from legacy without downtime
- **Emerging AI angle**: Scribe integration shows how AI evolves within product
- **Large-scale coordination**: Shows how shared infrastructure enables care continuity
- **Measurable outcomes**: Faster financial assistance, reduced data re-collection

#### Teardown Structure
1. **The Problem** – MSWs losing patient context; repetitive data collection
2. **The Architecture** – How Care360 unified data across 6+ EMRs + DataHive
3. **The Migration** – Replacing NeMSW across 20+ institutions without disruption
4. **The Workflows** – Financial assistance, case tracking, referrals, compliance
5. **The AI Evolution** – How Scribe emerged and eventually became standalone
6. **The Impact** – Care coordination across institutions; faster financial assistance

#### Who Should Care
- Healthcare leaders managing multi-institutional networks
- Chief Data Officers managing health data interoperability
- Product teams in regulated environments (payment systems, social services)
- Policy makers designing health system coordination

#### Key Metrics to Feature
- All public hospitals + VWOs in Singapore now on Care360
- Complete migration from legacy system (2023–2025)
- 1,000+ MSWs using Scribe (AI integration)
- 2,500+ conversations processed monthly via Scribe
- Pan-cluster backbone ensuring continuity across institutions

---

### 3. **HAS: "Prevention Through Frictionless UX at Scale"**

#### The Story
Most healthcare bookings are episodic (I'm sick, I call) or missed (I didn't know I was due for a mammogram). HAS shifted Singapore's health system from reactive to proactive by making preventive appointments frictionless and visible.

#### Key Angles
- **Eligibility as UX Feature**
  - Citizens see exactly which vaccines/screenings they're due for
  - Powered by National Immunisation Registry + medical records integration
  - Removes information asymmetry (citizens don't know what they need)
  - Clinic-initiated outreach via SMS campaigns

- **Aggregation + Discoverability**
  - All vaccines in National Adult Immunisation Schedule
  - Screen for Life diagnostics (mammograms, ultrasound, spirometry)
  - Healthier SG consultations and screenings
  - vaccine.gov.sg as public education + routing layer
  - Google Maps integration for walk-in discovery

- **Measurable Behavior Change**
  - 100k+ completed appointments per quarter
  - Approaching 2/3 coverage of CHAS GP clinics island-wide
  - Demonstrated uptake improvements for specific campaigns (HPV, pneumococcal)
  - Strong NPS with both public users and clinics

- **System Design Insight: Prevention Requires Visibility + Frictionless Access**
  - Knowing you're due isn't enough; booking must be effortless
  - Clinic integration (admins manage slots) reduces coordination overhead
  - SMS outreach creates "push" when citizens might otherwise ignore "pull"

#### Why It's a Strong Case Study
- **Clear product decisions**: Eligibility tools, SMS campaigns, clinic integration
- **Measurable user behavior**: 100k+ quarterly appointments, increasing coverage
- **Preventive care angle**: Addresses top-level health system goal
- **Platform evolution**: Emerged from COVID vaccination system → sustained capability
- **Generalizable UX patterns**: Eligibility visibility + discovery + frictionless booking

#### Teardown Structure
1. **The Problem** – Reactive healthcare; missed preventive opportunities
2. **The UX Design** – Eligibility tools, clinic admin portals, discovery
3. **The System Integrations** – NIR, Healthier SG, vaccine.gov.sg, Google Maps
4. **The Rollout Strategy** – Clinic-by-clinic expansion; outreach campaigns
5. **The Measurement** – 100k+ quarterly appointments; NPS tracking; coverage metrics
6. **The Shift** – How one product moves entire healthcare system from reactive to proactive

#### Who Should Care
- Health system leaders (prevention-focused strategy)
- Product managers designing consumer health products
- UX designers building for healthcare / government
- Policy makers evaluating preventive health strategies

#### Key Metrics to Feature
- 100k+ appointments per quarter
- 2/3 coverage of CHAS clinics island-wide
- Strong NPS (both user segments)
- Demonstrated uptake improvements for HPV, pneumococcal campaigns
- Integrated with 4+ downstream systems (vaccine.gov.sg, HealthierSG, Google Maps, clinic booking)

---

### 4. **ROOSTER: "High-Stakes Alerting & Operational Safety"**

#### The Story
Critical lab results (life-threatening values) need clinician attention within ~1 hour. Manual call-tree systems were brittle. Rooster built a rule-based, SMS-driven alerting system with measurable SLAs—and proved that narrow, focused tooling can transform high-stakes operations.

#### Key Angles
- **High-Stakes, Low-Volume Design Pattern**
  - 414 critical results/day (high throughput, but specific)
  - Must-reach systems (not nice-to-have)
  - Clear success metric: 97% acknowledged within 1 hour
  - SLA violations = patient safety risk

- **Architecture for Operational Clarity**
  - Result filters with configurable thresholds + age/admission rules
  - Clinician directory with posting and on-call roles
  - Monthly/daily roster management (bulk Excel upload support)
  - Routing rules with escalation levels
  - SMS alerting with 1/2/3 response codes (acknowledge/reject/"not my patient"/escalate)
  - Critical Result Dashboard for operations teams

- **Measurable Safety Improvements**
  - 7-minute median acknowledgement time (vs. manual system delays)
  - 97% of SMS alerts acknowledged within 1 hour
  - ~30% reduction in "no response" events (vs. baseline)
  - ~38% reduction in "not my patient" responses (via routing refinement)
  - Operational visibility into failure modes

- **MVP to Scale**: Live across 7 institutions (NHG, NUHS); planned expansion to all PHIs

#### Why It's a Strong Case Study
- **Narrow, well-defined problem**: Easier to tell compelling story
- **Clear impact correlation**: Better alerting → fewer missed results → better outcomes
- **Measurable SLAs**: 97% within 1 hour; 7-min median response
- **Operations-focused**: Shows product design for operational excellence (not just user-facing)
- **Scalable model**: Roster management, routing rules can scale to more institutions

#### Teardown Structure
1. **The Problem** – Critical results reaching clinicians too slowly; manual systems fragile
2. **The Architecture** – Result filters, clinician routing, SMS escalation
3. **The Operations Model** – Roster management, rule configuration, escalation paths
4. **The Measurement** – SLA tracking; response time distributions; outcomes correlation
5. **The Rollout** – Institution-by-institution expansion with training
6. **The Impact** – Measurable safety improvements; reduced clinical risks

#### Who Should Care
- Healthcare operations leaders (safety, efficiency)
- Clinical informatics teams
- Incident response / high-reliability organizations
- Product teams in safety-critical environments (aviation, finance, emergency response)

#### Key Metrics to Feature
- 414 critical results handled daily
- 7-minute median acknowledgement time
- 97% acknowledged within 1 hour (SLA)
- ~30% reduction in no-response events
- ~38% reduction in routing failures
- 7+ institutions live; expansion planned

---

## Tier 2: Strong Secondary Angles

### 5. **SCRIBE: "On-Prem AI in Regulated Environments"**

#### The Story
MSWs spend significant time documenting conversations. Scribe runs AI entirely on government infrastructure (no external APIs), transcribes and summarizes conversations, freeing up time for care.

#### Key Angles
- **Privacy-First AI Architecture**
  - All inference runs on government infrastructure (never leaves Singapore)
  - No external APIs or cloud dependencies
  - Meets data residency and governance requirements
  - Open-source models (not proprietary)

- **Local Language Tuning**
  - Speech recognition tuned for local accents (English, Chinese, Malay, Singlish)
  - Asynchronous processing (post-session, not live)
  - Handles cultural context in healthcare conversations

- **Rapid Productization**
  - Hackathon MVP (Jan 2024)
  - Productionized and piloted (April 2024)
  - Full rollout across public hospital MSW teams (Aug–Oct 2024)
  - Embedded initially in Care360, later standalone for broader use

- **Emerging Integration Pattern**
  - LLM-powered Care360 summaries (2025): "Quick case context" for MSWs
  - Shows how AI can enhance domain expertise rather than replace it

#### Why It's a Strong Case Study
- **Regulatory compliance angle**: Template for government health tech within data residency requirements
- **Rapid iteration**: Hackathon → production in <12 months
- **Thoughtful scope**: Narrow application (healthcare workers) reduces risks
- **Local language story**: Often overlooked in AI discussions

#### Limitations
- Narrower use case than Bright/Care360 (healthcare workers only)
- Less proven than other products (recent launch)
- But: Unique regulatory/AI angle valuable for specific audiences

#### Key Metrics to Feature
- 1,000+ MSWs using Scribe
- 2,500+ conversations processed monthly
- 100% on-prem (no external APIs)
- Built in <12 months (hackathon → production)
- Supporting 4 local languages

---

### 6. **REFERRAL EXCHANGE (RefX): "Infrastructure Layer Thinking"**

#### The Story
OGP is building a backend layer to digitize all healthcare referrals in Singapore. Instead of each product building its own integrations, RefX provides a stable, shared interface to all healthcare IT systems.

#### Key Angles
- **Hub-and-Spoke Architecture**
  - Single stable interface for upstream systems (EMRs, Bright, other referral tools)
  - Consolidates APIs from all major healthcare IT systems
  - Implements cross-cutting concerns: auth, logging, schema evolution, SLAs, monitoring
  - Enables future referral logic to move into shared infrastructure

- **Strategic Pattern Shift**
  - From: Product-centric (each system owns its integrations)
  - To: Infrastructure-centric (shared layers enable multiple downstream products)
  - Implication: Future products focus on UX/workflows, not integration plumbing

#### Why It's a Strong Case Study (For Specific Audiences)
- **Architecture and platform thinking**: For CTOs, architects
- **Reduces friction for downstream teams**: Shows how shared infrastructure scales
- **Enables product teams to move faster**: They focus on domain problems, not integrations

#### Limitations
- Still in development (less proven than other products)
- Narrower audience (architects, platform engineers)
- Strongest as context/pattern rather than standalone case study

#### Key Metrics to Feature
- Already referenced in Bright for Active Ageing Centre referrals
- Hub consolidating APIs from 6+ major healthcare IT systems
- Expected to enable multiple downstream products

---

## Tier 3: Supporting Patterns

### 7. **COVID-to-PEACETIME TRANSITION: "Crisis-to-Sustained Capability"**

#### The Story
COVID-19 forced rapid innovation. OGP built vaccination infrastructure in 2 weeks, scaled it to 13M+ doses, then thoughtfully sustained and repurposed it for peacetime health initiatives (HealthierSG, etc.).

#### Key Angles
- **Timeline of Repurposing**
  - COVID Vax Appointment System (built in 2 weeks) → HAS (merged into general preventive health)
  - GoWhere health sites (COVID response) → Repurposed for HealthierSG
  - CMB (vaccination backbone) → Model for future health data interoperability

- **Implication**: Crisis-driven tech that's thoughtfully maintained can become institutional capabilities

#### Why It's Strong as Context
- Explains how OGP "earned the right" to build healthcare tech
- Shows organizational learning and capability-building
- Provides narrative bridge between crisis innovation and sustained value

#### Limitations
- More of a pattern than a standalone case study
- Strongest as introduction/context to other products (HAS, CMB)

---

## Case Study Bundle Ideas

Rather than separate documents, you could create **thematic collections**:

### Bundle A: "Process & Operations Design"
- **Bright** (process-first design)
- **Rooster** (operations for high-stakes environments)
- **Audience**: Operations leaders, product managers in regulated sectors

### Bundle B: "Data Architecture & Interoperability"
- **Care360** (unified patient profile across EMRs)
- **Referral Exchange** (hub-and-spoke backend)
- **COVID Management Backbone** (single source of truth)
- **Audience**: CTOs, data architects, healthcare IT leaders

### Bundle C: "AI in Regulated Environments"
- **Scribe** (on-prem LLM/ASR)
- **Care360 + Scribe integration** (AI-powered summaries)
- **Audience**: Policy makers, compliance officers, AI practitioners in regulated sectors

### Bundle D: "Prevention & Consumer Health"
- **HAS** (frictionless preventive appointments)
- **HealthierSG integration** (outreach campaigns)
- **Audience**: Health system leaders, consumer health product managers

---

## Recommended Development Priority

### Immediate (Most ROI)
1. **Bright** – Universal appeal; process design methodology; clear narrative
2. **Care360** – Large-scale system replacement; interoperability angle; emerging AI

### High Priority (Strong Angles, Specific Audiences)
3. **HAS** – Preventive care UX; measurable behavior change; generalizable patterns
4. **Rooster** – Operations/safety angle; well-defined problem; measurable SLAs

### Medium Priority (Valuable, Narrower Scope)
5. **Scribe** – Regulatory/AI angle; strong for specific audiences (policy, compliance)
6. **RefX** – Architecture pattern; strongest as context to Bright/Care360

### Context/Supporting
7. **COVID-to-Peacetime** – Pattern/narrative bridge between products

---

## Next Steps

For each case study, you'd want to:
1. **Develop narrative arc** (problem → discovery → design → rollout → impact)
2. **Extract product decisions** (what made this work?)
3. **Quantify impact** (metrics, outcomes, success measures)
4. **Identify learnings** (what would other organizations apply?)
5. **Create visual aids** (architecture diagrams, rollout timelines, user flows)

Would you like me to dive deeper into any specific product angle?
