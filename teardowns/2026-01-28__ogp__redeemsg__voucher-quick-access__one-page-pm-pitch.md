# One-page PM pitch (case study): Reduce re-login + link hunting for vouchers (RedeemSG)

## TL;DR
Users repeatedly lose the voucher entry point because it arrives via SMS and opens in a mobile browser tab that’s easy to bury. The fix is to offer a persistent shortcut right after successful voucher retrieval: **“Save voucher for quick access”** (Add to Home Screen / Save shortcut). This reduces repeat friction for the two highest-frequency jobs: **purchase** and **check balance**.

---

## 1) Problem
### User pain
- Voucher link is delivered via **SMS** (transient). After the first open, users often need to **hunt the SMS again**.
- Re-opening the voucher requires **Singpass re-login** to retrieve the voucher link again.
- This is extra painful because it happens on *repeat visits*, when users expect it to be fast.

### Most common jobs-to-be-done
1) **Use voucher for purchase** (need quick access at point-of-sale)
2) **Check voucher balance** (quick lookup)

### Why now
- The system already works for first-time redemption. The highest leverage is removing repeat friction.

---

## 2) Current journey (today)
1) User receives SMS with voucher link
2) User taps link → opens in mobile browser
3) User authenticates via Singpass
4) Voucher page shown

Repeat visit:
- Browser tab is lost or user didn’t save it → user goes back to SMS → re-opens link → re-auth via Singpass

---

## 3) Proposed change (MVP)
### Intervention
After successful voucher page load (post-auth), show a lightweight in-product banner:

**“Save this voucher for quick access”**
- Primary CTA: **Save**
- Secondary: **Not now**
- Helper text: “Use this to quickly open your voucher when purchasing or checking balance.”

### What “Save” does (implementation options)
Option A (lowest engineering risk): **Add to Home Screen guidance**
- Trigger PWA Add-to-Home-Screen if supported
- Otherwise show OS-specific instructions (iOS Safari vs Android Chrome)

Option B (still simple, more polished): **Create a stable “voucher hub” entry point**
- Saved shortcut opens a landing page that routes user to voucher experience (may still require Singpass)

---

## 4) Success metrics
### Primary
- Reduction in **repeat re-auth events** per active user (proxy: repeat voucher sessions requiring Singpass)
- Increase in **repeat voucher opens** (7-day / 30-day retention for voucher page)

### Secondary
- Reduction in support contacts: “can’t find voucher link” / “need link again”
- Median **time-to-voucher** on repeat visit

---

## 5) Rollout plan
1) **Instrument** baseline: repeat visits, re-auth frequency, time-to-voucher
2) Launch banner to a small % of users
3) Measure uptake: CTR “Save”, successful add-to-home-screen completion (where measurable)
4) Iterate copy/placement
5) Expand rollout

---

## 6) Risks / constraints (and how we handle them)
- **Security constraints:** voucher access may require re-auth each time.
  - That’s acceptable: we’re reducing the *hunt step* even if auth remains.
  - Copy should set expectation: “You may be asked to verify with Singpass again.”

- **OS limitations (iOS A2HS UX):** limited ability to prompt programmatically.
  - Provide clear instructions + remember “Not now” for X days.

- **User trust:** avoid feeling spammy.
  - Only show after successful voucher display; frequency cap; dismissible.

---

## 7) Why this is a Pair-style win
- Focused on a high-frequency workflow
- Low-risk, incremental change
- Clear success metrics
- Improves experience without requiring a full redesign
