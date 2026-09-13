# Erdős #890 ↔ #1093 — divisor-window bridge program

**Author:** Jared Wilder  
**Status:** structural reduction and exact finite frontier program; no blanket claim that either parent problem is solved.

This repository is the canonical public home for the estate's #890/#1093 bridge: the large-prime binomial identity, deficiency/excess bookkeeping, admissible LCM divisor-window reduction, finite deficiency engine, exact frontier records, and the forensic history connecting the two problem routes.

## Core idea

The program turns divisibility constraints on binomial coefficients into a constrained divisor-window problem around an LCM scale. The #890 and #1093 routes meet through a large-prime binomial bridge, after which deficiency data and admissibility conditions can be handled exactly for finite parameter ranges.

## Source layout

Exact public source bytes are migrated under:

- `bridge/` — the broad #890↔#1093 extraction package;
- `compact/` — the compact proved-lemma mirror;
- `divisor-window/` — the focused #1093 theorem/computation surface.

Historical workflow labels are not treated as novelty certificates. Finite frontiers remain finite; conditional reductions remain conditional.
