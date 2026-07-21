# ROSS 2026 workshop paper

The Overleaf root document is `sigconf.tex`.

Current title:

> Guarding HEFT-Style Placement against MSI-Induced Locality Conflicts in
> Multi-GPU Task Graphs

The draft uses the repository's ACM `sigconf` template and includes:

- the formal HEFT--MSI locality-conflict construction;
- prefix-safe copy-aware HEFT and its exact no-prefix ablation;
- the controlled fixed-successor SALC certificate;
- the qualified 180-run, six-treatment, Williams-counterbalanced matrix;
- the historical clean 30-run gate triplet as supporting strong-opportunity evidence;
- one-run copy-model sensitivity with explicit evidence boundaries;
- two vector figures and a fully specified bibliography.

The primary clean result is source-locked to
`e3cfeaf36b6a8e3c4b3a1754270aa2ecde09647a` and contains all 180 expected
executions. Cholesky and LU are the two effective modeled-copy-opportunity
cases; FDTD, CG, and MiniWeather are H/P/N placement- and copy-identical timing
controls. Prefix-safe improves over HEFT by 1.313x and 1.177x on Cholesky and
LU, respectively, and is compared against global weighted-copy and unique-
owner locality baselines. Nineteen of the thirty workload--scheduler group
medians exceed the 5% scheduler-share target, while all six CG groups meet it.

Prefix-safe scheduling is presented as a general admission rule for the
HEFT--MSI conflict, not as a Cholesky/LU-specific policy. The strongest repeated
speedups still come from two dense configurations selected after exploration,
so they are condition-specific evidence rather than an estimate of prevalence.
The completed five-workload confirmation separates actionable opportunities,
identical-decision controls, simple locality baselines, conservative gate cost,
and gate-removal over-optimization. All current configurations use deferred,
fully materialized DAG submission and therefore do not validate dynamic task
arrival.

The primary protocol is one current-source 180-run block: five workloads
(FDTD, standard CG, Cholesky, LU, and MiniWeather), six treatments, and six
repeat blocks. Within each workload, the six-sequence Williams design assigns
every treatment to every order position once and balances every distinct
directed first-order adjacency once. The strict calibration rule requires 7/9
inliers plus the scaled-MAD gate. Its timings are not pooled with the historical
30-run block.

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
and email placeholders in `sigconf.tex` before submission. The result-bearing
artifact commit is `58cb4c57a3279d79f7b2205d5eb42a1016e53425`, but an anonymous HTTP
request to the code repository returned 404 on 2026-07-21. Publish a reviewer-
accessible archive and replace the explicit access-controlled notice in the
manuscript before submission.

## Local build

Compile `sigconf.tex` with pdfLaTeX/BibTeX or with Overleaf's normal LaTeX
workflow. The committed `acmart.cls` and `ACM-Reference-Format.bst` make the
project self-contained.
