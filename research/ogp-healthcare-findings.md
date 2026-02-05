# OGP Healthcare Product Analysis: Key Findings for Teardown

## Executive Summary

Open Government Products (OGP) has built a **tiered, interconnected healthcare technology ecosystem** in Singapore spanning preventive care, clinical operations, social care, and public health infrastructure. This analysis distills key product learnings, architectural patterns, and strategic insights from their healthcare portfolio for case study documentation.

---

## 1. Portfolio Architecture: Three-Tier Model

OGP organizes healthcare products into distinct tiers, each serving different functions within the health ecosystem:

### **Tier 1: Dedicated Healthcare Products**
Core, purpose-built health products with explicit healthcare focus:

| Product | Domain | Launch | Status | Key Metric |
|---------|--------|--------|--------|-----------|
| **HAS** (Health Appointment System) | Vaccination & preventive screening booking | 2022 | Active, expanding | 100k+ appointments/quarter |
| **Care360** | Medical Social Work (MSW) case management | 2023 | Active, expanding | All public hospitals + VWOs |
| **Bright** | ILTC referral platform | 2024 | Phased national rollout | 5,000+ healthcare workers trained |
| **Rooster** | Critical results alerting & clinical rostering | 2024 | Active in NHG, NUHS | 414 critical results/day |
| **RefX** (Referral Exchange) | Backend referrals API layer | 2024 | In development | Hub-and-spoke model |
| **Scribe** | AI transcription & case note assistant | 2024 | 1,000+ users | 2,500+ conversations/month |

### **Tier 2: Health-Specific Infrastructure & COVID Systems**
Foundational systems built specifically for health data and pandemic operations:

- **COVID-19 Management Backbone (CMB)**: Central "single source of truth" for vaccination & test records; fed 13M+ doses through system
- **COVID-19 Vaccination National Appointment System**: Built in 2 weeks; later merged into HAS
- **Sync**: Consent-based platform for sharing verified COVID test & vaccination records with employers/organizations
- **GoWhere Health Sites**: Location-based directories (VaccineGoWhere, ARTGoWhere, TestCentreGoWhere, FluGoWhere, MaskGoWhere)

### **Tier 3: Generic Platforms with Health Use Cases**
Cross-cutting government tools repurposed heavily in health:

- **FormSG**: Forms automation (COVID volunteer recruitment, etc.)
- **GoWhere Suite**: Multi-campaign microsites (22M+ visits across health campaigns)
- **PaySG & RedeemSG**: Payment/voucher platforms (COVID swab tests, mask distribution)
- **ActiveSG**: Sports & fitness booking (population health)
- **Postman, Isomer, For.sg**: Mass communications and site-building

**Strategic insight**: This tiering prevents siloing while allowing reuse of proven infrastructure across domains.

---

## 2. Product Deep Dives: Key Learnings

### **Health Appointment System (HAS) — Preventive Care Shift**

**Problem solved**: Episodic, reactive healthcare booking; limited visibility into recommended vaccinations/screenings

**Key features**:
- Eligibility tools showing which vaccines/screenings citizens are due for (based on age, medical records)
- GP admin portal for slot management and Healthier SG outreach
- Integration with National Immunisation Registry (NIR) for medical eligibility checks
- Vaccine Advisor for clinicians (AI-powered decision support)
- Clinic-initiated outreach via SMS campaigns
- Google Maps integration for walk-in discovery

**Ecosystem role**: Central hub for preventive health, incorporating:
- All vaccines in National Adult Immunisation Schedule
- Screen for Life diagnostics (mammograms, ultrasound, spirometry)
- Healthier SG consultations and screenings
- Vaccine.gov.sg as public education & routing layer

**Scale & impact**:
- Handling 100k+ completed appointments per quarter
- Approaching 2/3 coverage of CHAS GP clinics island-wide
- Strong NPS with both public users and clinics
- Creates measurable funnels for HPB/MOH campaigns (e.g., HPV, pneumococcal uptake)

**Teardown angle**: **How platforms shift entire care models from episodic to preventive** through frictionless booking + automated outreach

---

### **Care360 — Social-Care Backbone**

**Problem solved**: MSWs re-collected same patient info (financial hardship, social issues) across institutions; manual financial assistance; fragmented referrals

**Replaced legacy system**: NeMSW (siloed, institution-specific)

**Key capabilities**:
- Unified patient profile pulling data from EMRs and government sources (via Vault, then DataHive)
- End-to-end referral and case tracking across institutions
- Digital financial assistance workflows with SMS delivery vs. paper forms
- Audit logs and institutional reporting for compliance

**Rollout scope**:
- All 12 SingHealth PHIs + 6 NHG PHIs + 2 additional NHG PHIs + all 6 NUHS PHIs
- Complete migration from NeMSW (2023)
- Onboarded all 4 VWO community hospitals (2024–2025)
- Integrated with NGEMR, Sunrise Clinical Manager, NeFR, MFEC, SSNet

**AI integration (Scribe)**: Care360 became anchor for applied AI in health:
- MSW-patient conversations transcribed and summarized into Care360 drafts
- 2025: LLM-powered patient profile summaries for quick case orientation
- Later deprecated embedded Scribe in favor of standalone platform

**Impact**:
- Digitized, standardized financial assistance workflows (faster approvals for straightforward cases)
- Reduced repetitive data collection (patients don't re-tell traumatic histories)
- Operational visibility dashboards for critical cases
- Pan-cluster backbone ensuring MSWs don't lose patient context across institutions

**Teardown angle**: **Social-care as equal to clinical care; data integration as coordination mechanism** across fragmented institutions

---

### **Bright — ILTC Referral Platform**

**Problem solved**: IRMS (legacy system) was slow, causing 3–8 week referral delays that delayed hospital discharge and community placement

**Key insight from design philosophy**:
> "Most of the changes on Bright start with a process change. Then Bright just enables it."

This reflects a **process-first, technology-second** mindset—critical for healthcare digital transformation.

**Core capabilities**:
- Unified referral workspace with multi-organization collaboration
- Service matching by region, care needs, availability
- Bed-level vacancy management (different models for nursing homes, respite care, hospice)
- Prefilled biodata from government sources (DataHive) to reduce data entry
- Rich audit logs for governance

**Phased rollout**:
- **Phase 1 (Jan 2025)**: All nursing home, respite care, and sheltered home referrals transitioned
- **Phase 2–4 (mid–late 2025)**: Added 14 referral forms across daycare, home care, community mental health
- **Training**: 5,000+ healthcare professionals trained

**Process innovations enabled by Bright**:
- Direct referral assignment from hospital to provider (reduced hand-offs)
- Different vacancy models for hospice, psychiatric, community services
- Integration with downstream subsidy systems (MFEC, ILTC, SSNet) for seamless post-placement claims

**Teardown angle**: **Process redesign as prerequisite to successful platforms; referral bottlenecks as operational leverage point**

---

### **Rooster — Critical Results Alerting**

**Problem solved**: Critical lab/radiology results (life-threatening values) required action within ~1 hour; manual call-tree systems were brittle and slow

**Architecture**:
- Result filters with configurable thresholds and age/admission-status rules
- Clinician directory with posting and on-call roles
- Monthly/daily roster management (bulk Excel upload support)
- Routing rules with escalation levels
- SMS alerting with 1/2/3 response codes (acknowledge/reject/"not my patient"/escalate)
- Critical Result Dashboard for operations teams

**Performance (Q3–Q4 2024)**:
- 414 critical results handled daily
- Median acknowledgement time: ~7 minutes
- 97% of SMS alerts acknowledged within 1 hour
- ~30% reduction in "no response" events
- ~38% reduction in "not my patient" responses (via routing refinement)

**Scale**: Live across 7 institutions in NHG and NUHS clusters; planned expansion to remaining PHIs and Woodlands Health

**Teardown angle**: **High-leverage, narrow tooling for high-stakes, low-volume events; direct correlation between alerting speed and clinical outcomes**

---

### **Referral Exchange (RefX) — Backend Infrastructure Layer**

**Strategic pattern**: Moving from point-to-point integrations → hub-and-spoke model

**Vision**: Backend layer to digitize all healthcare referrals in Singapore, starting with subsidized specialist referrals

**Architecture**:
- Single, stable interface for upstream systems (EMRs, Bright, other referral tools)
- Consolidates APIs from all major healthcare IT systems
- Implements cross-cutting concerns: auth, logging, schema evolution, SLAs, monitoring
- Enables future referral logic to move into shared infrastructure

**Current role**: Already referenced in Bright for Active Ageing Centre referrals

**Implication**: Over time, more health capabilities expected to move into RefX rather than being baked into product-specific code

---

### **Scribe — On-Prem AI for Healthcare**

**Problem solved**: MSWs spend significant time documenting conversations; documentation delays care planning

**Key innovation**: Entire AI pipeline runs on government infrastructure (no external APIs)

**Technical approach**:
- Open-source speech recognition models tuned for local accents (English, Chinese, Malay, Singlish)
- Open-source LLMs running on OGP infrastructure
- Asynchronous processing (post-session transcription, not live)
- Sensitive patient data never leaves government systems

**Rollout**:
- Built as hackathon MVP (Jan 2024)
- Productionized and piloted (April 2024)
- Full rollout across public hospital MSW teams (Aug–Oct 2024)
- Embedded initially into Care360, later standalone platform for broader healthcare use

**Scale & impact**:
- 1,000+ MSWs using Scribe
- 2,500+ conversations processed monthly
- Substantial documentation time savings
- Future expansion to other healthcare workers beyond MSWs

**Teardown angle**: **Demonstrating that on-prem, regulated AI is viable; template for government health tech operating within data residency requirements**

---

## 3. Data Architecture & Interoperability

### **COVID-19 Management Backbone (CMB)**

**Role**: "Single source of truth" for vaccination and testing records across Singapore

**Data sources consolidated**:
- Vaccination data from vaccination centers, GPs, polyclinics
- Lab test results (PCR, serology, ART at clinics)
- Self-reported ARTs (uploaded and verified)

**Downstream consumers**:
- TraceTogether (vaccination + PET status)
- HealthHub
- Vaccine booking systems
- Referrals to entry restrictions, organizational compliance

**Scale**: Millions of test/vaccination statuses retrieved daily at pandemic peak

**Strategic insight**: Demonstrates that Singapore's public sector can run **population-scale, near-real-time health data services entirely within government infrastructure**.

### **DataHive Integration**

Both Care360 and Bright prefill citizen biodata from DataHive, reducing data entry errors and friction across products. This is a pattern of **shared data infrastructure enabling better UX** across multiple downstream products.

---

## 4. Pandemic to Peacetime Transition

### **Timeline of Evolution**

| Phase | Product | Timeline | Evolution |
|-------|---------|----------|-----------|
| **Crisis response** | COVID Vax Appointment System | Built in ~2 weeks | Rapid response to crisis |
| **Scale** | CMB, Sync, GoWhere sites | 2021–2022 | Integrated supporting infrastructure |
| **Generalization** | HAS (merged COVID vax system) | 2023 | Repurposed for all preventive health |
| **Peacetime expansion** | HealthierSGEventsGoWhere, vaccine.gov.sg | 2024–2025 | Evolved COVID infrastructure into sustainable programs |

### **Key Pattern: Crisis-Born → Productized → Sustained**

1. **COVID Vaccination National Appointment System** scaled to 13M+ doses
2. Later **merged into HAS** and evolved into general preventive health platform
3. GoWhere microsites created for COVID response **repurposed for HealthierSG**
4. CMB infrastructure model applied to future health data interoperability
5. Sync (employee health sharing) evolved from COVID operational needs

**Implication**: Crisis-driven tech that's thoughtfully maintained can become institutional capabilities.

---

## 5. Governance & Accountability Model

### **Public Report Cards**

All major products have public, detailed report cards at **reports.open.gov.sg** including:
- Usage metrics (appointments, conversations, critical results)
- Net Promoter Scores (both user segments)
- Feature timelines and release notes
- Audit logs and compliance tracking
- Performance metrics

**Examples**:
- HAS: 100k+ appointments/quarter, strong NPS, detailed vaccine coverage by clinic
- Rooster: 414 critical results/day, 7-min acknowledgement time, 97% SLA
- Scribe: 1,000+ users, 2,500+ conversations/month
- Bright: 5,000+ trained professionals, migration completion dates, service types added

**Strategic insight**: **Public transparency as accountability mechanism** for government health tech; enables external evaluation and builds public trust

---

## 6. Ecosystem Integration: End-to-End Care Journey

OGP's health-tech work spans the entire care continuum:

```
PREVENTION & EARLY DETECTION
├─ HAS + vaccine.gov.sg
├─ HealthierSGEventsGoWhere
└─ ActiveSG
    → Drive preventive vaccination, screening, lifestyle change

CLINICAL CARE & PATIENT SAFETY
├─ Rooster (critical results alerting)
└─ CMB (consistent vaccination/test view)
    → Ensure critical results reach clinicians fast
    → Guarantee consistent data across systems

HOSPITAL-TO-COMMUNITY TRANSITIONS
├─ Care360 (MSW workflows + social-financial support)
├─ Bright (ILTC referrals)
└─ Referral Exchange (RefX) backend
    → Digitize and rationalize referral pathways
    → Reduce hand-offs and delays

FRONTLINE PRODUCTIVITY & AI
├─ Scribe (AI transcription)
└─ LLM-powered Care360 summaries
    → Reduce documentation burden
    → Provide faster clinical context

PUBLIC-ORGANIZATION DATA FLOWS
├─ Sync (employee health sharing)
└─ GoWhere (public directories)
    → Demonstrate patient-mediated data sharing
    → Create ubiquitous, simple public interfaces
```

---

## 7. Strategic Takeaways for Healthcare Product Leaders

### **Architecture Pattern**

OGP consistently builds:
- **Thin, focused UIs** (HAS, Bright, Rooster) solving specific pain points
- **Robust backends** exposing clear APIs to integrate existing systems (CMB, RefX)
- **Reusable shared stacks** (GoWhere, FormSG, DataHive) reducing duplication
- **Pattern**: Microproduct strategy with shared infrastructure

### **Process Change First, Tech Second**

Both Bright and Care360 examples show that successful healthcare platforms:
1. Start with **deep process analysis** (workflow mapping, stakeholder interviews)
2. **Redesign workflows** before building software
3. Implement tech as enabler, not driver

> "Most of the changes on Bright start with a process change. Then Bright just enables it." — OGP/AIC team

### **On-Prem, Privacy-First AI**

Scribe demonstrates that **regulated-environment AI is viable**:
- No external APIs; all inference on government infrastructure
- Open-source models tuned for local context
- Meets data residency and governance requirements
- Practical example for other government health systems

### **Interoperability Trajectory**

RefX, CMB, and DataHive integration suggest healthcare tech is shifting from:
- **Product-centric**: Each system owns its integrations
- **Infrastructure-centric**: Shared layers (RefX for referrals, CMB for health records) enable multiple downstream products

**Implication**: Future products will focus on UX and domain-specific workflows, not integration plumbing.

### **Measurement & Accountability**

Public report cards create:
- External accountability (metrics are published)
- Product clarity (teams know what success looks like)
- User trust (transparency into performance and impact)

---

## 8. Quantifiable Impact Summary

| Product | Scale | Impact |
|---------|-------|--------|
| **HAS** | 100k+ appointments/quarter, 2/3 CHAS clinic coverage | Shifted system to preventive care; measurable vaccination/screening uptake campaigns |
| **Care360** | All public hospitals + VWOs; pan-cluster | Eliminated repetitive data collection; faster financial assistance approvals |
| **Bright** | 5,000+ trained professionals | Reduced referral times from 3–8 weeks (baseline unknown, but significant operational improvement) |
| **Rooster** | 414 critical results/day, 7-min median response | 97% acknowledged within 1 hour; ~30% fewer no-response events |
| **Scribe** | 1,000+ users, 2,500+ conversations/month | Substantial documentation time savings for MSWs |
| **COVID infrastructure** | 13M+ vaccine doses administered | Enabled rapid pandemic response; infrastructure repurposed for peacetime |

---

## 9. Implications for Case Study / Teardown Documentation

### **What to highlight**:

1. **Tiered product architecture** as organizational model for healthcare tech
2. **Process-first design philosophy** as prerequisite to platform success
3. **Shared infrastructure layers** (RefX, CMB, DataHive) enabling product teams to focus on UX/workflows
4. **Public report cards** as governance and accountability model
5. **Crisis-to-sustained-capability** pathway for crisis-born tech
6. **On-prem AI as viable** within regulated environments
7. **End-to-end journey mapping** showing how products connect across prevention, clinical care, transitions, and public health

### **Who should care**:

- **Health system leaders** evaluating digital transformation strategies
- **Policy makers** designing health tech regulation and investment
- **Product teams** building healthcare platforms (especially in public/regulated sectors)
- **Government technology organizations** exploring best practices in health tech

---

## References

- OGP public report cards: https://reports.open.gov.sg
- Bright case study: GovInsider's "Process Change as Driving Force Behind OGP's Bright Product Success"
- Scribe article: OpenGovSG Substack, "3 Lessons from Launching Scribe"
- Source research: Comprehensive OGP healthcare analysis (ogp-healthcare.md)
