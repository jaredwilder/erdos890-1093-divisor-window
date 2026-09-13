# Erdős #1093 — finite-census correction record

**Author:** Jared Wilder  
**Audit date:** 2026-09-11

The universal divisor-window reduction in this directory is logically separate from historical finite enumeration tables. The release-day counterexample sweep recovered several errors in those older finite tables. They are recorded here so they cannot be silently re-imported into the valid reduction.

## Out-of-domain witnesses

Historical “minimal witness” records `(3,2)` and `(2,2)` violate the campaign's canonical admissible-domain condition `n>=2k`. They are not witnesses for the scoped finite census.

The pair `(6,2)` also kills an old blanket assertion that every admissible `k=2` pair has positive deficiency: its deficiency is zero.

## Incorrect deficiency labels

The pairs

`(22,4)` and `(23,4)`

were historically listed in a deficiency-1 set. Exact recomputation gives deficiency **0** for both.

A separate historical `k=5` census is falsified by the concrete pair

`(23,5)`.

That witness should be treated as a hard regression test for any regenerated table.

## Scope of the correction

These corrections do **not** refute the divisor-window theorem

`delta(n,k)=#{d|L_k : n-k<d<=n}`

for admissible `(n,k)`. They correct finite data produced downstream of it.

The current README's published list of deficiency-`>1` cases through `k<=45` does not use `(22,4)` or `(23,4)` as positive cases; this file exists to prevent older campaign tables from being mistaken for the canonical finite census.

Any future regenerated full table should be produced directly from the divisor-window formula and must include these pairs as negative controls.
