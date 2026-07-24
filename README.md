# ROSS 2026 workshop paper

The Overleaf root document is `sigconf.tex`.

Current title:

> A Prefix-Safe Refinement of HEFT-Style Placement for Multi-GPU Task Graphs

The paper presents prefix-safe copy-aware placement, a bounded refinement of
HEFT-style scheduling for task-graph runtimes with software-managed data
residency. The scheduler evaluates lower-copy alternatives relative to HEFT
and admits one only when it does not extend the modeled completion of already
committed work.

## Evaluation at a glance

- Five workloads: FDTD, CG, Cholesky, LU, and MiniWeather.
- Six scheduler variants in six Williams-balanced repeat blocks, for 180
  primary observations.
- Cholesky and LU are the placement--residency opportunity cases; FDTD, CG,
  and MiniWeather are identical-placement timing controls for H/P/N.
- Prefix-safe improves over HEFT by 1.313x on Cholesky and 1.177x on LU while
  reducing scheduler-modeled copy by 81.0% and 38.8%, respectively.
- An exact no-prefix ablation exposes both sides of the admission trade-off:
  removing the gate helps Cholesky but harms LU.
- A source-distinct 30-run block reproduces the effective-case directions.
- Copy-model sensitivity, scheduler-cost measurements, and a controlled
  fixed-successor migrate--return trace delimit and validate the mechanism.

The manuscript contains four vector figures, five tables, and 26 references.
The paper reports scheduler-modeled copy quantities rather than
profiler-measured physical traffic.

## Local build

Compile `sigconf.tex` with pdfLaTeX and BibTeX, or use Overleaf's normal LaTeX
workflow. The committed `acmart.cls` and `ACM-Reference-Format.bst` keep the
project self-contained.
