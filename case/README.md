# C07 · Centre segregation and inclusion bands in casting — W27–W30

> **Real industrial case dossier.** Copied from the authoritative case card in
> `CASES.md` §4 so this repository stays self-contained after it is pushed to
> GitHub. Planning links: [`CASES.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/CASES.md) ·
> [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md) ·
> [`WEEKLY_PLAN.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/WEEKLY_PLAN.md).
> **Evidence level: A + B** · No plant data is held in this repository.

**Repository:** `e07-cfd-macrosegregation` · **Evidence: A + B** ·
**References:** R16, R17, R18, R21, R31, Y2R04, Y2R05, Y2R06, Y2R16.

**Industrial problem.** Continuously cast slabs show centre inclusion bands found
by ultrasonic testing of rolled plate (Y2R05, Y2R16); a 231 t steel ingot shows
positive segregation in the hot top and negative at the bottom (Y2R06). Both
cause rejected plate and forgings.

**Why it happens.** Solute rejected at the solidification front, buoyancy-driven
flow, and argon-bubble/inclusion capture in the mushy zone.

**Data (open + journal).** Voller–Prakash (R16) and Bennon–Incropera (R17)
benchmarks (A, fully reproducible); published centreline C/S profiles and UT
maps (B, digitised with stated uncertainty).

**Tool chain.** `libthermo` enthalpy–porosity → 2D FVM + SIMPLE (R20) → solute
transport (R17, R18) → Lagrangian particle tracking with capture criterion
(Y2R04, Y2R16) → MPI scaling → GCI → OpenFOAM cross-code comparison →
digitised-profile comparison.

**What each reference validates.**
- R16, R17, R18 — phase-change and two-phase transport formulation.
- R21 — macro-to-microstructure bridge.
- R31 — V&V and GCI reporting.
- Y2R05, Y2R16 — LES inclusion-entrapment models (external plant comparison).
- Y2R06 — 231 t ingot measured profiles (external, digitised).

**Deliverables.** `cases/ingot_231t/`, `cases/cc_inclusions/`; `case.yml`; GCI
table; digitisation note; shell-thickness check; particle-capture map; MPI
scaling plot; cross-code report.

**Validation.** Energy and solute conservation with errors; GCI reported;
digitisation error stated **separately** from model error; UT comparison labelled
external.

**Acceptance.** Positive/negative segregation zones reproduced; B-level
disclaimer present; cross-code difference quantified.

## Claim boundary

See [`evidence.md`](evidence.md) for the evidence level and the exact wording
that must be used when quoting literature numbers. All datasets and references
are listed in [`sources.md`](sources.md); the four-week execution plan is in
[`week_plan.md`](week_plan.md).
