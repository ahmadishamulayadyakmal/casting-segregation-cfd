# Centre segregation and inclusion bands in casting (C07)

## Industrial problem

Continuously cast slabs show centre inclusion bands found by ultrasonic testing of rolled plate; a 231 t steel ingot shows positive segregation in the hot top and negative at the bottom. Both cause rejected plate and forgings.

**Why it happens.** Solute rejected at the solidification front, buoyancy-driven flow, and argon-bubble/inclusion capture in the mushy zone.

## Data (no plant data)

Mixed: Voller–Prakash (R16) and Bennon–Incropera (R17) benchmarks are fully reproducible from the cited equations; published centreline C/S profiles and UT maps are digitised with stated uncertainty and treated as external literature. No plant data is held.

> Only open datasets and published literature are used. No plant or proprietary data are held here; plant numbers quoted from papers are external literature, not independently reproduced results.

## Tool chain

Modern Fortran 2D FVM + SIMPLE, `libthermo` enthalpy–porosity, solute transport, Lagrangian particle tracking, MPI, GCI, OpenFOAM cross-code comparison, Python digitisation with uncertainty.

## Journal references

- **R16** ([DOI](https://doi.org/10.1016/0017-9310(87)) — phase-change fixed-grid benchmark.
- **R17** ([DOI](https://doi.org/10.1016/0017-9310(87)) — binary continuum transport formulation.
- **R18** — two-phase macrosegregation model (compound: 2 papers).
- **R20** — FVM/SIMPLE discretisation.
- **R21** — macro-to-microstructure bridge.
- **R31** — V&V, GCI and digitisation reporting.
- **Y2R04** ([DOI](https://doi.org/10.1016/j.powtec.2015.10.025)) — inclusion-cluster motion in a continuous caster.
- **Y2R05** ([DOI](https://doi.org/10.1007/s11837-018-3118-3)) — LES inclusion entrapment; external plant comparison.
- **Y2R06** ([DOI](https://doi.org/10.2355/isijinternational.54.351)) — 231 t ingot measured profiles (external, digitised).
- **Y2R16** ([DOI](https://doi.org/10.3390/met11040654)) — inclusion capture in a slab caster.

## Deliverables

`cases/ingot_231t/`, `cases/cc_inclusions/`; `case.yml`; GCI table; digitisation note; shell-thickness check; particle-capture map; MPI scaling plot; cross-code report.

## Validation & claims

Energy and solute conservation with errors; GCI reported; digitisation error stated SEPARATELY from model error; UT comparison labelled external; positive/negative segregation zones reproduced.

## Limitations

B-level disclaimer required. Digitised figures carry their own uncertainty; cross-code agreement is not plant validation.

## Repository layout

- `README.md` — case summary, data policy, method, results and limitations.
- `CONTRIBUTING.md` — how to propose changes.
- `docs/index.md` — documentation map.
- `docs/model_card.md` and `docs/vv_template.md` — reporting templates.
- `.github/workflows/ci.yml` — automated checks.

Only open data and published literature are used. No plant or proprietary data
are included. All artefacts are written in English.
