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
- ✅ **Pushed 2026-07-06:** repo initialized and pushed to
  https://github.com/jamescanode-alt/Kaiser-Benefit-Resource-Guide (private, branch `main`,
  commit `3378ed9`). Contents: the guide, all 101 SPD `.md` conversions, and project logs.
  **PDFs (1.2 GB) are gitignored and remain local only**, per user direction; the
  `Colorado/Webinars/*.pptx` files also remain local.
- Open follow-ups tracked in TODO.md (advisor contacts, "Confirm in SPD" multipliers,
  physician/special-plan appendix, per-region reduction factors).

---

## 2026-07-08 — Verified Kaiser Guide Accessibility

### Summary
- Confirmed `Kaiser_Retirement_Benefits_Guide.html` is committed and pushed to the main branch.
- Users can now access the guide directly from the GitHub repository.
- File is self-contained and can be opened locally in any browser.

### Status
- ✅ Guide is accessible in the repository at:
  https://github.com/jamescanode-alt/Kaiser-Benefit-Resource-Guide
- ✅ Pushed commit `95f002b` documenting task completion.
- ✅ Guide ready for advisors to download and use.
- ✅ GitHub Pages deployed and live at:
  https://jamescanode-alt.github.io/Kaiser-Benefit-Resource-Guide/
- ✅ Repository made public and Pages enabled.
- ✅ `.nojekyll` file added to resolve deployment (commit `dd29e68`).

---

## 2026-07-08 — Guide review pass: clarity, insights, lump-sum rate sensitivity

### Summary
Implemented the approved content review of `Kaiser_Retirement_Benefits_Guide.html`
(commit `c4adeac`), focused on new-advisor comprehension:

- **Section 01:** "Day-one quick reference" table — the five numbers that drive most
  Kaiser conversations (vesting, ER gate, reduction range, married default, TSA auto-enroll).
- **Section 02:** the three service definitions (Hour / Year / Credited) converted from a
  dense paragraph to a table, plus a part-time 1,000-vs-2,000-hour insight note.
- **Section 03:** worked example extended with an age-60 companion case ($1,275/mo at 85%)
  bridging the formula to the early-start reduction.
- **Section 04:** dated "$330,000 in 2023" IRS pay-cap figure generalized to indexed-limit
  language routed to the KPRC (accuracy/compliance).
- **Section 05 + estimator:** new warning that the subsidized reduction schedule belongs to
  active-service retirees; deferred vested benefits typically face steeper actuarial
  reductions. Caveat added to the estimator callout and its JS note.
- **Section 07 (user-flagged as critical):** full lump-sum interest-rate sensitivity
  treatment — segment-rate mechanics, inverse relationship, lookback/stability-period
  timing, a three-step "how to use this with a client" playbook, and a
  commencement-timing trap callout. Comparison cards fixed (J&S inflation con added;
  RMD line clarified for Roth; rate-sensitivity con added to lump sum).
- **Section 11:** first-meeting question set converted to a 7-item checklist.
- **Section 13:** glossary entries added/extended (Segment rates; Deferred Vested).
- **Hero:** 55-word lead sentence split in two.
- **TODO:** added mobile left-rail fallback and catch-up-contribution follow-ups; fixed
  stale "not a git repository" note.

### Validation
- HTML parser check: tags balanced, 14/14 sections, all anchors resolve, no new bare
  entities (20 pre-existing ones are in dropdown labels/JS and unchanged).
- Browser preview: no console errors; all 8 new content blocks render; selector →
  estimator flow re-tested (Georgia 1.3% → $1,300/mo); no horizontal overflow at 375px.

### Status
- ✅ Pushed to main (`c4adeac`); live via GitHub Pages after cache refresh.
- Design-hook flags (Helvetica, side-tab accents) left as-is — inherited intentionally
  from the approved AT&T template per the 2026-07-05 entry.

---

## 2026-07-08 — Removed Farther / Focus Team branding

### Summary
Stripped all "Farther" and "Focus Team" references from the published pages
(commit `155e48f`), per user direction:
- **Guide:** nav brand is now "Advisor Field Guide / KAISER PERMANENTE"; hero lead says
  "a new wealth advisor"; Section 08 lens and Section 10 tax disclaimer de-branded;
  Section 14 contacts heading renamed to "Advisor team" (placeholders unchanged);
  footer title now "Kaiser Permanente Retirement Benefits · Advisor Field Guide".
- **Landing page:** title "Kaiser Benefit Resource Guide"; logo removed; tagline
  "Advisor Resources".
- **TODO.md:** contacts item reworded to match the renamed section.
- Historical PLAN_LOG/CHANGE_LOG entries intentionally retain the old name as a record.

### Validation
- Grep across `*.html`: zero remaining matches for Farther / Focus Team.
- Browser preview: both pages render, estimator intact (3 result cards), landing page
  screenshot confirmed clean.

### Status
- ✅ Pushed to main (`155e48f`); live via GitHub Pages after cache refresh.
