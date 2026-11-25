# Centre segregation and inclusion bands in casting (C07)

> Workspace folder: `e07-cfd-macrosegregation` · Suggested GitHub repository: `casting-segregation-cfd`
> Epic: E07 · Weeks: W27–W30 · Evidence level: **A + B**
> Master specification: [`CASES.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/CASES.md) §4 · Download the papers: [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md)

## Industrial problem

Continuously cast slabs show centre inclusion bands found by ultrasonic testing of rolled plate; a 231 t steel ingot shows positive segregation in the hot top and negative at the bottom. Both cause rejected plate and forgings.

**Why it happens.** Solute rejected at the solidification front, buoyancy-driven flow, and argon-bubble/inclusion capture in the mushy zone.

## Data (no plant data)

Mixed: Voller–Prakash (R16) and Bennon–Incropera (R17) benchmarks are fully reproducible (A); published centreline C/S profiles and UT maps are digitised with stated uncertainty (B). No plant data is held.

> The author cannot supply factory data. This project uses **only open datasets and
> credible peer-reviewed journals**. If this is a B-level case, the case report
> must contain the exact disclaimer from `CASES.md` §1 and must **never** claim
> plant validation.

## Tool chain

Modern Fortran 2D FVM + SIMPLE, `libthermo` enthalpy–porosity, solute transport, Lagrangian particle tracking, MPI, GCI, OpenFOAM cross-code comparison, Python digitisation with uncertainty.

## Journal references

- **R16** — phase-change fixed-grid benchmark.
- **R17** — binary continuum transport formulation.
- **R18** — two-phase macrosegregation model (compound: 2 papers).
- **R20** — FVM/SIMPLE discretisation.
- **R21** — macro-to-microstructure bridge.
- **R31** — V&V, GCI and digitisation reporting.
- **Y2R04** — inclusion-cluster motion in a continuous caster.
- **Y2R05** — LES inclusion entrapment; external plant comparison.
- **Y2R06** — 231 t ingot measured profiles (external, digitised).
- **Y2R16** — inclusion capture in a slab caster.

Each reference above is listed with its DOI or stable URL, access status and
manual download route in [`JOURNALS.md`](https://github.com/ahmadishamulayadyakmal/metallurgy-project/blob/main/JOURNALS.md) §4, and in the shared
BibTeX library `papers/references.bib`. Do not cite a paper you have not been
able to obtain; if it is inaccessible, record that in `JOURNALS.md` §8.

## Deliverables

`cases/ingot_231t/`, `cases/cc_inclusions/`; `case.yml`; GCI table; digitisation note; shell-thickness check; particle-capture map; MPI scaling plot; cross-code report.

## Validation & claims

Energy and solute conservation with errors; GCI reported; digitisation error stated SEPARATELY from model error; UT comparison labelled external; positive/negative segregation zones reproduced.

## Limitations

B-level disclaimer required. Digitised figures carry their own uncertainty; cross-code agreement is not plant validation.

## Definition of Done

1 merged PR · green tests · 1 new artefact · 1 README paragraph · 1 sprint note
`docs/sprints/wNN.md` · tag `wNN`. Before the case tag `c07` is created,
this README must contain all six sections: Industrial problem, Data (no plant
data), Tool chain, Journal references, Validation & claims, Limitations.

## Repository skeleton

Shared files: `CONTRIBUTING.md` (sprint contract), `.github/` (issue, PR and
CI templates), `docs/sprints/wNN.md`, `docs/vv_template.md` and
`docs/model_card.md`. `CASES.md`, `JOURNALS.md` and `REPOSITORIES.md` are in a
separate planning repository; their links above remain valid after this folder
is pushed as its own repository.

The real industrial case dossier is in `case/`: `README.md` (full case card),
`evidence.md`, `sources.md` and `week_plan.md`.

## Repository status and GitHub Desktop

This folder is already a Git repository on `main`, pushed to GitHub as
`casting-segregation-cfd` with an SSH `origin`. In GitHub Desktop, choose **Add local
repository** and select this folder; do not clone into the same path.

```bash
git status --short --branch
git pull --rebase origin main
git push origin main
```

Weekly work follows `CONTRIBUTING.md`: one PR, green tests, one artefact, one
README paragraph, `docs/sprints/wNN.md`, tag `wNN`. Tag `c07` only after
all six README sections are complete.


## Language

All artefacts in this repository are written in **English**.
