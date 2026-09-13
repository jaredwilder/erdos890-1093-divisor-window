# Erdős #1093 — forensic problem card

## Frozen canonical statement

For $n\geq 2k$ we define the deficiency of $\binom{n}{k}$ as follows. If $\binom{n}{k}$ is divisible by a prime $p\leq k$ then the deficiency is undefined. Otherwise, the deficiency is the number of $0\leq i<k$ such that $n-i$ is $k$-smooth, that is, divisible only by primes $\leq k$. Are there infinitely many binomial coefficients with deficiency $1$? Are there only finitely many with deficiency $>1$?

## Audit counts

- Registry events: 43
- PROVED: 2
- FALSE: 7
- COMPUTATION_SUPPORTED: 8
- UNTESTED: 11
- Cable KERNEL_CHECKED: 0
- Cable KERNEL_FAILED: 0
- Witness receipts: 0
- Lean files: 0

## Full registry chronology

- **line 1 / seq 1 / R001/— / ROUTE_OPENED:** 
- **line 2 / seq 2 / R002/— / ROUTE_OPENED:** 
- **line 3 / seq 3 / R001/L2 / COMPUTATION_SUPPORTED:** k=2 subfamily (n=2^a+1, a≥1) verified to give D=1 under the exact guard; this is evidence for clause (i) only, clause (ii) undetermined — no full close, no finite-reduction theorem available.
- **line 4 / seq 4 / R001/L1 / UNTESTED:** Input predicate finite(residual)∧concrete(reduction) evaluates FALSE exactly; certification aborts fail-closed.
- **line 5 / seq 5 / R001/L1 / PROVED:** L1 (deficiency=0 for all admissible k=2 pairs; deficiency(2,2)=2) is true but covers only one k, so it does not advance either clause of the two-question close.
- **line 6 / seq 6 / R001/L1 / UNTESTED:** Closure adjudicator's refusal stands: the deficiency=0 proof is verified only at k=2 (deficiency(2,2)=2); no exact rational/integer reduction covering the full admissible domain (all k≥1, n≥2k) is supplied, so branch A closure fails and L1 cannot be certified PROVED beyond the verified case.
- **line 7 / seq 7 / R001/L2 / UNTESTED:** No proved finite-reduction theorem transfers the single-subfamily computation to the full admissible domain; L1 covers only k=2, so branch A is not closed under either clause.
- **line 8 / seq 8 / R001/L3 / FALSE:** universal bound deficiency≤1 fails at (n,k)=(2,2) where deficiency=2
- **line 9 / seq 9 / R001/— / ROUTE_KILLED:** 
- **line 10 / seq 10 / R003/— / ROUTE_OPENED:** 
- **line 11 / seq 11 / R002/L1 / COMPUTATION_SUPPORTED:** Guard parity kills all multi-k-smooth windows for k=2,3 in n≤31 (no deficiency>1 instance found); finite range only, no transfer theorem.
- **line 12 / seq 12 / R002/all / UNTESTED:** no analytic reduction or residual claim supplied; certifier fails closed without a bound to verify
- **line 13 / seq 13 / R002/L1 / FALSE:** k=2 admits no admissible deficiency-1 pairs at all: guard forces n≡2,3 mod 4 but deficiency-1 forces n≡0,1 mod 4.
- **line 14 / seq 14 / R002/— / ROUTE_KILLED:** 
- **line 15 / seq 15 / R004/— / ROUTE_OPENED:** 
- **line 16 / seq 16 / R003/L2 / COMPUTATION_SUPPORTED:** admissibility for k=3 is exactly n≡11 mod 12 (Lucas, verified 2000, no exception)
- **line 17 / seq 17 / R003/ALL / UNTESTED:** residual claim "per contract" not instantiated; certificate scope undefined; fail-closed abort per K-rules, no sign determination available
- **line 18 / seq 18 / R003/L1 / PROVED:** deficiency(n,1)=1 for all n≥2 vacuously, so clause (i) is trivially affirmative unless k≥2 is imposed; clause (ii) remains open and is the only substantive target.
- **line 19 / seq 19 / R003/L1 / UNTESTED:** deficiency(n,1)=1 for all n≥2 vacuously, so clause (i) is trivially affirmative unless k≥2 is imposed; clause (ii) remains open and is the only substantive target.
- **line 20 / seq 20 / R003/L1 / FALSE:** k=1 edge case: deficiency(n,1)=0 for all n≥2, and L1 determines neither clause (ii); repair requires k≥2 restriction plus a proved clause-(i)→clause-(ii) transfer or a second standing lemma.
- **line 21 / seq 21 / R003/— / ROUTE_KILLED:** 
- **line 22 / seq 22 / R005/— / ROUTE_OPENED:** 
- **line 23 / seq 23 / R004/L1 / COMPUTATION_SUPPORTED:** Exhaustive exact sweep over 2k≤n≤2000, k≤60: max deficiency 3 at (3,3) uniquely, deficiency 2 at (2,2) uniquely; counterexamples L-C1 (deficiency 0 at (15,3)) and L-C3 (non-monotonicity) both FALSE.
- **line 24 / seq 24 / R004/unsupplied / UNTESTED:** No lemma, residual bound, or certificate object in packet; certifier fails closed rather than fabricating a target.
- **line 25 / seq 25 / R004/L1 / UNTESTED:** as literally stated L1 may be trivially true via the k=1 1-smooth convention (every n works, zero primes p≤1), a prime-edge-case artifact; to be a genuine candidate it must restrict to k≥2 and prove nondegenerate infinitude — untested as repaired.
- **line 26 / seq 26 / R004/L1 / FALSE:** Family (2^a+1,2) fails the prime guard (C(n,2) even for all a≥2), so deficiency is undefined; repair requires admissible k≥3 constructions passing the guard with exactly one k-smooth n−i.
- **line 27 / seq 27 / R004/— / ROUTE_KILLED:** 
- **line 28 / seq 28 / R006/— / ROUTE_OPENED:** 
- **line 29 / seq 29 / R005/L1 / COMPUTATION_SUPPORTED:** family (2·3^b+1,3) yields infinitely many admissible deficiency-1 pairs, verified exactly for b≤8 with general residue argument; clause (ii) remains open.
- **line 30 / seq 30 / R005/certifier / UNTESTED:** No exact residual or interval data supplied; fail-closed, no certificate issued.
- **line 31 / seq 31 / R005/L1 / FALSE:** Counterexample (n,k)=(11,2): guard passes, deficiency is 0, not 1; primality of n makes the n-entry non-k-smooth for all k≥2.
- **line 32 / seq 32 / R005/— / ROUTE_KILLED:** 
- **line 33 / seq 33 / R007/— / ROUTE_OPENED:** 
- **line 34 / seq 34 / R006/L1 / COMPUTATION_SUPPORTED:** Exhaustive exact enumeration for k=3, 6≤n≤60 under the Lucas guard: deficiency-1 at n=15,35,39; deficiency-2 at n=7; 0 at n=23,31; n=55 excluded by guard — finite certificate only, canonical questions untouched.
- **line 35 / seq 35 / R006/ALL / UNTESTED:** No analytic reduction or concrete residual claim supplied; certificate scope empty, abort fail-closed.
- **line 36 / seq 36 / R006/L1 / FALSE:** Counterexample C(11,5)=462 divisible by primes 2,3 ≤ 5; prime guard fails, and infinitude inference was a partial-close anyway.
- **line 37 / seq 37 / R006/— / ROUTE_KILLED:** 
- **line 38 / seq 38 / R007/L1 / COMPUTATION_SUPPORTED:** All 40 slices exceed proportion 0.15 of defined pairs with deficiency ≥ 2; finite-range verified, no implication for the canonical unbounded claims.
- **line 39 / seq 39 / R007/all / UNTESTED:** Contract supplies no concrete analytic reduction (none) and no finite/numerical residual certificate ("per contract" is undefined); no exact rational/interval verifier can be instantiated without dependencies, scope, and stated residual bounds — failing closed per contract, no silent tolerance appli
- **line 40 / seq 40 / R007/L1 / FALSE:** For k=2 the prime guard excludes all n with a power of 2 among {n, n−1} (mod-4 check), so deficiency-1 pairs are empty at k=2 and the infinitude lemma fails.
- **line 41 / seq 41 / R007/— / ROUTE_KILLED:** 
- **line 42 / seq 42 / R008/— / ROUTE_OPENED:** 
- **line 43 / seq 43 / R008/L1 / COMPUTATION_SUPPORTED:** Deficiency-1 dominates the computed window (k≤50,n≤2000) with zero deficiency≥3 sightings, but this is finite-window evidence only, not a proof of either canonical clause.

## Release note

This card is historical forensic material. It intentionally preserves contradictions in the campaign chronology rather than silently harmonizing them. Later Pass-3 derived mathematics in this directory is a separate surface and should not be read back into these source-recorded statuses.
