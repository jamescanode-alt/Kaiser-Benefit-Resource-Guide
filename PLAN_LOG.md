# PLAN_LOG

## 2026-07-05 — Kaiser Retirement Benefits Guide (advisor field guide)

**Task:** Build a single-file HTML "Kaiser Retirement Benefits Guide" for new Farther
wealth advisors, using the AT&T Benefit Resource Guide
(https://jamescanode-alt.github.io/ATT-Benefit-Resource-Guide/) as the template for
layout, structure, and formatting. Left rail must include a dropdown of all plans/unions
derived from the .md files in the Kaiser subfolders.

**Source material:** 100 Summary Plan Descriptions (converted from PDF to .md) across 11
region/group folders. Retirement content lives in the "RETIREMENT PROGRAMS" section of
each SPD.

**Plan architecture confirmed from SPDs:**
- Core: **Kaiser Permanente Retirement Plan (KPRP)** — qualified defined-benefit pension.
  Formula = **plan multiplier × Final Average Monthly Compensation (FAMC) × Years of
  Credited Service**. Multiplier varies by group: 1.2% / 1.3% / 1.4% / 1.45% / 1.5%
  (some groups blend, e.g. pre-2009 service at 1.5%).
- FAMC = highest 60 consecutive months (of last 120) of monthly comp rate (hourly base
  × 173.33).
- Vesting: 5 Years of Service (or age 65 while employed).
- Early Retirement: age 55 + 15 YOS, OR age + service ≥ 75 ("Rule of 75"); reduction
  table 60% @55 → 100% @65.
- Payment forms: Single Life, 50/66⅔/75% J&S, Lump Sum.
- DC plans: **Tax-Sheltered Annuity (TSA, 403(b))** — Vanguard, auto-enroll 2%→6%,
  pre-tax + Roth; **Supplemental Savings and Retirement Plan (SSRP)** — ~5% auto employer
  contribution, 100% vested.
- Special cases: CPMG (Colorado physicians) = cash balance; TPMG physician plans differ;
  Stationary Engineers Local 39 = standalone multiemployer (Taft-Hartley) pension;
  Washington = Group Health Cooperative transition offsets.

**Deliverable:** `Kaiser_Retirement_Benefits_Guide.html` (self-contained, Farther-branded,
navy/cream/gold design matching AT&T template) with:
- Left rail: brand + plan/union dropdown (optgroups = regions, 100 options) + numbered nav.
- Sections: landscape, eligibility/vesting, the pension formula, FAMC, early retirement /
  Rule of 75, interactive pension estimator, payment options, TSA/SSRP savings plans,
  retiree medical, IRMAA/Roth, strategy playbook, protections, glossary, contacts.
- Interactive: pension estimator (multiplier × FAMC × service with early-retirement
  reduction) driven by the selected plan's multiplier.

**Risks / notes:** Multipliers and factors vary by CBA and plan year; guide is training
only and repeatedly directs advisors to verify actual figures in the KPRC / official SPD.
Accuracy-first per compliance standards; no fabricated figures.

**Next steps:** Build HTML, verify visually at desktop + mobile, update CHANGE_LOG/TODO.

---

## 2026-07-08 — Make Kaiser Guide Accessible on GitHub

**Task:** Commit and push the existing `Kaiser_Retirement_Benefits_Guide.html` to GitHub so users can access it directly. The guide provides advisors with comprehensive Kaiser retirement benefits information organized by region and plan type.

**Objective:** Ensure the HTML file is available in the repo for users to download, open locally, or access via GitHub Pages.

**Files involved:**
- `Kaiser_Retirement_Benefits_Guide.html` (existing, ~197KB)
- All regional SPD source materials (supporting documentation)

**Next steps:** Push to main, update CHANGE_LOG.md.

---

## 2026-07-08 — Content review pass: clarity, insights, streamlining

**Task:** Implement the approved review findings in `Kaiser_Retirement_Benefits_Guide.html`:
1. Deferred-vested vs. active-retirement reduction distinction (Section 05 + estimator caveats).
2. Day-one quick-reference table (Section 01).
3. Second worked example bridging the formula and the early-start reduction (Section 03).
4. **Expanded lump-sum interest-rate sensitivity explainer in Section 07** (user-flagged as
   critical advisor concept) + segment-rates glossary entry.
5. Accuracy fixes: generalize the dated $330,000/2023 IRS pay-cap figure; clarify the RMD
   note (Roth exempt); add missing cons to the J&S comparison card.
6. Streamlining: split the hero lead; convert the three service definitions to a table;
   convert the first-meeting question set to a checklist.

**Risks:** All new quantitative language stays hedged and routed to KPRC/SPD per compliance
standards; no specific rate/dollar figures asserted as current. Mobile left-rail fallback
deferred to TODO.

**Next steps:** Edit HTML, validate structure, push, update CHANGE_LOG/TODO.

---

## 2026-07-08 — Remove Farther / Focus Team branding

**Task:** Strip all "Farther" and "Focus Team" references from the two user-facing pages
(`Kaiser_Retirement_Benefits_Guide.html`, `index.html`), replacing them with neutral
advisor-guide branding. Historical log entries retain the old name as a record.

**Files:** guide (nav brand, hero lead, Section 08 lens, Section 10 disclaimer,
Section 14 contacts, footer), index.html (title, logo/tagline), TODO.md (contacts item).

**Next steps:** Verify in preview, push, update CHANGE_LOG.
