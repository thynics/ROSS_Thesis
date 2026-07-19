# ROSS 2026 workshop paper

The Overleaf root document is `sigconf.tex`.

Current title:

> Guarding the HEFT Prefix: Copy-Aware Locality Refinement and a One-Hop
> Chain Certificate for Multi-GPU Task Graphs

The draft uses the repository's ACM `sigconf` template and includes:

- the formal HEFT--MSI locality-conflict construction;
- prefix-safe copy-aware HEFT and its exact no-prefix ablation;
- the controlled fixed-successor SALC certificate;
- the qualified clean 30-run gate triplet as two strong HEFT--MSI opportunity observations;
- one-run copy-model sensitivity with explicit evidence boundaries;
- two vector figures and a 15-entry bibliography.

The primary clean result is source-locked to
`cfdd6d1ff8f1c45c8c9c0da62a859452dce09b86`: prefix-safe beats HEFT in all
10 paired observations with a 1.241084514x paired geomean. The draft also
retains the negative deployment result that every clean scheduler group exceeds
the 5% scheduler-share target.

Prefix-safe scheduling is presented as a general admission rule for the
HEFT--MSI conflict, not as a Cholesky/LU-specific policy. The current strongest
repeated evidence comes from two dense configurations selected after
exploration, so their speedups are condition-specific evidence rather than an
estimate of prevalence across applications. The ongoing expanded five-workload
confirmation is designed to separate actionable opportunities, safe weak/no-opportunity
cases, and gate-removal over-optimization. All current configurations use
deferred, fully materialized DAG submission and therefore do not validate
dynamic task arrival.

## Remaining metadata

ROSS is single-blind. Replace the explicit author, affiliation, city, country,
and email placeholders in `sigconf.tex` before submission. A public, immutable
artifact URL and final source tag must also replace the artifact placeholder.

## Local build

Compile `sigconf.tex` with pdfLaTeX/BibTeX or with Overleaf's normal LaTeX
workflow. The committed `acmart.cls` and `ACM-Reference-Format.bst` make the
project self-contained.
