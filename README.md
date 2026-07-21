# ROSS 2026 workshop paper

The Overleaf root document is `sigconf.tex`.

Current title:

> Guarding HEFT-Style Placement against MSI-Induced Locality Conflicts in
> Multi-GPU Task Graphs

The draft uses the repository's ACM `sigconf` template and includes:

- the formal HEFT--MSI locality-conflict construction;
- prefix-safe copy-aware HEFT and its exact no-prefix ablation;
- the controlled fixed-successor SALC certificate;
- the qualified 75-run five-workload problem-boundary matrix;
- the historical clean 30-run gate triplet as supporting strong-opportunity evidence;
- one-run copy-model sensitivity with explicit evidence boundaries;
- two vector figures and a 15-entry bibliography.

The primary clean result is source-locked to
`673f8c19d73280be02733b806285339ee8699950` and contains all 75 expected
executions. Cholesky and LU are the two effective modeled-copy-opportunity
cases; CG and MiniWeather are neutral/non-degrading no-opportunity controls;
FDTD's latency gain has no modeled-copy signal and is retained without being
counted as mechanism evidence. No workload-level geomean regresses. Eleven of
the fifteen primary workload--scheduler group medians exceed the 5% scheduler-
share target, while all three CG groups and MiniWeather no-prefix meet it.

Prefix-safe scheduling is presented as a general admission rule for the
HEFT--MSI conflict, not as a Cholesky/LU-specific policy. The strongest repeated
speedups still come from two dense configurations selected after exploration,
so they are condition-specific evidence rather than an estimate of prevalence.
The completed five-workload confirmation separates actionable opportunities,
safe no-opportunity cases, a gain without mechanism signal, and gate-removal
over-optimization. All current configurations use deferred, fully materialized
DAG submission and therefore do not validate dynamic task arrival.

The primary protocol is one current-source 75-run block: five workloads
(FDTD, standard CG, Cholesky, LU, and MiniWeather), three exact gate variants,
and five repeats. It uses the pre-performance `scalar_microkernel_v2`
calibration rule: ordinary tasks retain the 7/9 inlier requirement, while only
launch-bound tasks with at most 24 bytes of footprint and a median below
0.050 ms use a 6/9 central-majority requirement plus the unchanged scaled-MAD
gate. Its timings are not pooled with the historical 30-run block.

The primary analysis froze its interpretation bands before unified results
were read: geomean speedup at least 1.03x is material, 0.97x to below 1.03x is
neutral/non-degrading, and below 0.97x is a reported regression. A positive
reduction in scheduler-modeled copy bytes is evaluated separately as the
mechanism-opportunity signal.

Gate effect is also predeclared as a direct paired prefix-safe versus no-prefix
comparison. A 1.03x geomean in either direction is material: prefix-safe winning
with a more aggressive no-prefix copy reduction is an over-optimization
counterexample, while no-prefix winning is reported as conservative gate cost.
Neither outcome changes the independent HEFT-relative problem classification.

## Remaining metadata

ROSS is single-blind. Replace the explicit author, affiliation, city, country,
and email placeholders in `sigconf.tex` before submission. A public, immutable
artifact URL and final source tag must also replace the artifact placeholder.

## Local build

Compile `sigconf.tex` with pdfLaTeX/BibTeX or with Overleaf's normal LaTeX
workflow. The committed `acmart.cls` and `ACM-Reference-Format.bst` make the
project self-contained.
