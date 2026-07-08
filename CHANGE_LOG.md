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

---

## 2026-07-08 — Government reference links added throughout the guide

### Summary
Added authoritative .gov links wherever the guide discusses official tables, limits, or
rates (commit `2467996`):
- **Sec 01:** ssa.gov on the Social Security pillar.
- **Sec 04:** IRS COLA dollar limits (the FAMC pay cap and maximum-pension limits).
- **Sec 07:** IRS minimum present value segment rates (linked inline where segment rates
  are introduced) and IRS rollover rules in the tax-mechanic callout.
- **Sec 08:** IRS 403(b) contribution limits; IRS designated-Roth FAQs.
- **Sec 09:** HealthCare.gov (pre-65 marketplace pricing) and medicare.gov eligibility.
- **Sec 10:** SSA "how income affects your Medicare premiums" (IRMAA tier tables) added
  next to the existing medicare.gov link.
- **Sec 12:** PBGC maximum-guarantee tables, DOL EBSA QDRO publication, IRS RMD FAQs.
- **Sec 14:** new "Government references (current tables, limits & rates)" section — a
  12-item annotated link list consolidating all of the above.

### Validation
- Every URL checked before publishing: 10 returned HTTP 200 via curl; ssa.gov and dol.gov
  block automated fetchers (403), so their canonical URLs were confirmed via search index.
  One candidate IRS RMD URL 404'd and was replaced with the live RMD-FAQs page.
- HTML parser: tags balanced, no errors. All 12 external URLs in the file match the
  verified set; every external link uses target="_blank" rel="noopener".
- Browser preview: 25 external anchors render, estimator intact, no console errors;
  Section 14 list screenshot confirmed.

### Status
- ✅ Pushed to main (`2467996`); live via GitHub Pages after cache refresh.

---

## 2026-07-08 — Case studies and worked scenarios added

### Summary
Added seven teaching scenarios so new advisors see the rules applied, not just stated
(commit `5d541c6`). All figures derive from the guide's existing representative values
(1.2–1.5% multipliers, the NCAL Salaried reduction schedule); every person is labeled an
illustrative composite; unsourced factors (J&S conversion, actuarial deferred-vested
reductions) stay qualitative with KPRC pointers.

- **Sec 02:** "The four-year offer" vesting-cliff scenario (Priya — leaving 9 months
  early forfeits ~$435/mo for life) + sick-leave conversion scale check (~$44/mo,
  honest framing).
- **Sec 04:** "The overtime myth" (Rosa — $30k of final-year OT changes the pension by
  zero; a $2/hr base raise doesn't) and "The phase-down that costs less than feared"
  (Vic — FAMC is a rate, so part-time only slows Credited Service, ~1.2 yrs over 3 yrs).
- **Sec 05:** "What one more year buys" (Nadia — $1,949 → $2,157/mo, ~11% permanent
  raise) + "The fork in the road" (Ana/Ben — 18 months determines which reduction table
  applies for life), appended to the deferred-vested callout.
- **Sec 07:** "Three clients, three different right answers" — Elena (J&S; survivor's
  resources), Devon (lump sum; legacy), Sam (health-impaired longevity; spouse already
  protected). Each names the deciding factor.
- **Sec 10:** "The December conversion" IRMAA cliff scenario ($400 over a tier → both
  spouses pay the surcharge two years later); no hard-coded thresholds.
- **Sec 11:** "Denise" capstone — an 8-row table applying every playbook step to one
  client (NorCal CNA, 1.45%, $8,200 FAMC, 22 yrs; $1,962 vs $2,426/mo at 58 vs 60),
  closed by a "what the case shows" lens.
- Sec 08 deliberately skipped per the review recommendation.

### Validation
- All 15 arithmetic claims re-computed by script and matched to the published text.
- HTML parser: tags balanced, 14/14 sections, no errors.
- Preview: all 7 scenarios render; Denise table = 8 rows; vignette grid = 3 cards;
  estimator intact; no console errors; no horizontal overflow at 375px.

### Status
- ✅ Pushed to main (`5d541c6`); live via GitHub Pages after cache refresh.

---

## 2026-07-08 — Case-study fixes + interactive conversion

### Summary
Two commits:
1. **`a9cacdf` — readability fixes (user-reported):** moved the "illustrative composite"
   note directly under the Section 11 case-study header; fixed the unreadable
   dark-on-dark <em> ("after") in the navy lens box with a `.lens em` rule (bold italic,
   inherited light color) rather than a new color. Audit found this was the only <em> on
   a dark background; the rule protects future ones.
2. **`53774c8` — interactive case study:** the Denise capstone is now an 8-step exercise.
   Each playbook step poses a question; a correct answer reveals that step's explanation
   and unlocks the next. Numeric steps: multiplier (1.45), age-58 factor (75%), the
   pension math ($2,616 / $1,962 with rounding tolerance), Medicare gap (7 yrs).
   Multiple-choice steps: segment-rate direction, married payout default, 403(b) first
   moves, IRMAA lookback (correct answers spread across positions). Wrong answers show a
   section-specific hint; after two misses a "Show the answer" escape appears. The
   summary table + "what the case shows" lens are hidden until completion, then revealed
   under a "Case complete" banner. Vanilla JS/CSS in the guide's existing idiom.

### Validation
- HTML parser: tags balanced, 8 cs-steps, single script block.
- Preview click-through: full correct run (8/8 → banner + revealed summary), wrong-answer
  hint path, two-miss reveal path, Enter-key submit, disabled inputs after completion.
- `.lens em` computed style confirmed: rgb(219,229,245), italic, weight 700.
- No console errors; no horizontal overflow at 375px.

### Status
- ✅ Pushed to main (`a9cacdf`, `53774c8`); live via GitHub Pages after cache refresh.
