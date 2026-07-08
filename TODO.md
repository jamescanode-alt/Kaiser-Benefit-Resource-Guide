# TODO — Kaiser Retirement Benefits Guide

## Open items / follow-ups

- [ ] **Fill in advisor team contacts** in Section 14 (currently placeholders
      "Add advisor name & contact"). Do not fabricate names.
- [ ] **Confirm pension multipliers marked "Confirm in SPD"** for the ~24 groups where the
      formula phrasing wasn't auto-detected (physician plans, DC-only, benefit-band, or
      differently-worded SPDs). Notably: several Washington groups (KPWA OPEIU/SEIU/UFCW,
      NONREP), some SoCal locals (L501, L7600, UFCW_RX, PSWC), MAS L2-OPTRX / L99,
      NW L701 / L555, NC Genetics Counselors, Residents, Maui NUE.
- [ ] **Physician & special plans need their own treatment:** CPMG (cash balance), TPMG
      Retirement Plans 1/2/3, Stationary Engineers Local 39 (multiemployer/Taft-Hartley).
      The standard estimator does not model these — consider a dedicated appendix.
- [ ] **Verify the early-commencement reduction schedule per region.** The guide uses the
      NCAL Salaried table (60% @55 → 100% @65) as representative; confirm whether other
      regions/contracts differ and note exceptions.
- [ ] **Retiree medical:** the Modified Retiree Medical Benefit eligibility/subsidy rules
      vary by region and were summarized at a high level. Expand once the H&W SPDs are
      reviewed in depth.
- [ ] **Duplicate source files:** `SPD_NC_SAL (1).md`, `SPD_NC_TPMG (1).md`,
      `SPD_TPMGRet123 (1).md` are duplicate copies (labeled "alt. copy" in the dropdown).
      Confirm whether the originals should be de-duplicated in the library.
- [ ] **Savings-plan match details** (employer % / match / true-up) vary by CBA and were
      summarized generally. Confirm per group from the savings-plan SPDs.
- [ ] **Mobile navigation:** below 980px the entire left rail (plan selector + section nav)
      is `display:none` with no fallback, so phone users cannot select a plan or jump to
      sections. Add a collapsible menu / inline selector for small screens.
- [ ] **Catch-up contributions (Section 08):** the guide does not yet mention the age-50
      catch-up or the 403(b) 15-year-service catch-up. Confirm availability in the
      savings-plan SPDs before adding (relevant to long-tenured Kaiser employees).
- [ ] **Case-study duplication:** the interactive case study now lives in both
      `Kaiser_Retirement_Benefits_Guide.html` (Section 11) and the standalone
      `Kaiser_Case_Study.html`. Any content change to one must be mirrored in the other
      (questions, answers/tolerances, reveals, summary table, lens).

## Notes
- Guide is training-only; every quantitative section directs advisors to verify with the
  KPRC and the controlling SPD (compliance-first).
- Repo: https://github.com/jamescanode-alt/Kaiser-Benefit-Resource-Guide (public); guide is
  live via GitHub Pages at https://jamescanode-alt.github.io/Kaiser-Benefit-Resource-Guide/.
