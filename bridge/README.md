# Erdős #890 ↔ #1093: large-prime / deficiency accounting bridge

**Author:** Jared Wilder  
**Public release:** 2026-09-11  
**Status:** derived pure-mathematics extraction; neither open problem is claimed solved.

## 1. Two exact identities

For a length-`k` binomial window, define `ω_{>k}(m)` to be the number of distinct prime divisors of `m` that exceed `k`.

Because

`C(n+k-1,k) = [n(n+1)...(n+k-1)]/k!`,

and no prime `p>k` divides `k!`, while such a prime can divide at most one of the `k` consecutive integers `n,...,n+k-1`, one gets the exact identity

`Σ_{i=0}^{k-1} ω_{>k}(n+i) = ω_{>k}( C(n+k-1,k) ).`

This is the recovered #890 large-prime binomial identity.

Now write each window value as

`n+i = a_i b_i`,

where `a_i` contains the prime factors `≤k` and `b_i` contains the prime factors `>k`. Let

`d = #{ i : b_i = 1 }`

and

`E = Σ_{b_i>1} (ω(b_i)-1)`.

Then, purely by counting the first large prime of each nontrivial `b_i` separately from its extras,

`S_k := Σ_i ω(b_i) = (k-d)+E`.

Therefore

`S_k ≤ k  ⇔  E ≤ d`.

This is the recovered deficiency/excess accounting identity.

## 2. Link to Erdős #1093

Under the #1093 admissibility condition, deficiency counts the positions in the relevant `k`-window whose values are `k`-smooth. Those are exactly the positions with `b_i=1`, so the same integer `d` becomes the #1093 deficiency count.

Thus, on an admissible window, #890's large-prime count can be read as

`large-prime burden = k - deficiency + excess multiplicity`.

The inequality side of #890 becomes the sharply local condition

`excess large-prime multiplicity ≤ deficiency`.

This is a genuine structural bridge between the two campaigns: a smooth entry creates one unit of budget, while every large-prime part carrying a second, third, ... distinct large prime spends that budget.

## 3. #1093 divisor-window reduction

Let `L_k = lcm(1,...,k)`. The recovered Pass-3 theorem packet states that for an admissible #1093 pair `(n,k)`, any `k`-smooth member among `n,n-1,...,n-k+1` must in fact divide `L_k`. Conversely every divisor of `L_k` is `k`-smooth. Hence, within the source admissibility convention,

`δ(n,k) = #{ d | L_k : n-k < d ≤ n }`.

This turns fixed-`k` positive deficiency into finite divisor geometry in `L_k`.

Important scope point: the implication “`k`-smooth ⇒ divides L_k`” is **not** asserted for arbitrary integers; the admissibility hypothesis is load-bearing.

## 4. Exact computation recovered with the theorem

The independent divisor-enumeration engine was recorded as reproducing every then-listed deficiency `>1` example through `k≤45`, including

`δ(284,28)=9`,

and reporting no additional examples in that scanned range. This is a finite exact computation, not a proof of the global finiteness question.

## 5. What is and is not closed

This packet does **not** claim a solution of Erdős #890 or #1093. It releases the exact identities and reduction that survived the estate audit:

- large-prime binomial identity;
- admissible LCM divisor-window reduction;
- deficiency/excess accounting formula;
- finite exact deficiency engine through the stated range.

The next mathematical target suggested by the bridge is to control windows where the smooth-position deficiency pays for all excess large-prime multiplicity.

## Provenance

Recovered from the 2026-09-02 Day-2 historic haul, promoted rows 163, 216–218 and 232–234. Historical source statuses were `MANUAL_PROOF_RECONSTRUCTED`, `INDEPENDENT_EXACT_COMPUTATION`, `DERIVED_FUSION`, and Pass-3 fusion. Novelty was unresolved in the source and is not upgraded here.
