# CHANGE_LOG

## 2026-07-05 — PDF→Markdown conversion + Kaiser Retirement Benefits Guide

### Summary
1. Converted all **101 PDF SPDs** across the 11 Kaiser subfolders to `.md` files
   (via `pdftotext -layout`, saved alongside each PDF). All extractions verified non-empty.
2. Built **`Kaiser_Retirement_Benefits_Guide.html`** — a self-contained, Farther-branded
   advisor field guide for new wealth advisors, modeled on the AT&T Benefit Resource Guide
   for layout, structure, and formatting.

### The guide
- **Design:** navy/cream/gold Farther "FOCUS TEAM" system reused from the AT&T template
  (kept intentionally to match the reference; design-hook tells for side-tab accents and
  Helvetica are inherited from that approved template).
- **Left rail:** brand + a **plan/union dropdown** listing all 100 SPD groups, grouped by
  region (11 optgroups) + numbered section nav. Selecting a plan populates a "Selected plan"
  panel (region, multiplier, plan type) and auto-sets the pension estimator's multiplier.
- **14 sections:** landscape · eligibility & vesting · pension formula · FAMC · early
  retirement & Rule of 75 · interactive pension estimator · payment options · TSA/SSRP
  savings · retiree medical · IRMAA & Roth · strategy playbook · protections · glossary ·
  contacts.
- **Interactive estimator:** multiplier × FAMC × Credited Service, with the representative
  early-commencement reduction schedule (60% @55 → 100% @65), Early-Retirement/Rule-of-75
  eligibility logic, and cash-balance/physician-plan guardrails.

### Content accuracy (from the SPDs)
- Core plan = KP Retirement Plan (defined benefit): multiplier (1.2%–1.5% by group) × FAMC
  × Credited Service; vesting 5 yrs; early retirement 55+15 or age+service ≥ 75.
- DC plans = TSA 403(b) (Vanguard, auto-enroll 2%→6%, pre-tax/Roth) + Supplemental Savings
  (employer-funded, e.g. 5%, 100% vested).
- Documented exceptions: CPMG cash balance, TPMG physician plans, Local 39 multiemployer.
- Compliance-first: every quantitative claim directs advisors to verify with the KPRC and
  the controlling SPD; no fabricated names or figures (contacts left as placeholders).

### Validation
- Structure: 14/14 sections balanced, 1 script block, all nav anchors resolve, invalid
  `&frac23;` entity fixed to `&#8532;`.
- Visual: verified in preview at desktop (1280px) and mobile (375px) — responsive collapse
  works, **no horizontal overflow** at 375px.
- Interactive: dropdown → planbar → estimator flow tested (Georgia 1.3% → $1,300/mo;
  age-60 reduction 85% → $1,275/mo; CPMG correctly flagged cash-balance).

### Status
- ✅ Deliverable complete and verified locally.
- ⚠️ **Not pushed:** this project directory is **not a git repository** (no `.git`). Per the
  workflow, code should be pushed to main, but there is no repo/remote configured here.
  To version and push, run (from the project root):
  ```
  git init
  git add PDF/.md files, Kaiser_Retirement_Benefits_Guide.html, PLAN_LOG.md CHANGE_LOG.md TODO.md
  git commit -m "feat: add Kaiser retirement guide + SPD markdown conversions"
  git remote add origin <remote-url>
  git push -u origin main
  ```
- Open follow-ups tracked in TODO.md (advisor contacts, "Confirm in SPD" multipliers,
  physician/special-plan appendix, per-region reduction factors).
