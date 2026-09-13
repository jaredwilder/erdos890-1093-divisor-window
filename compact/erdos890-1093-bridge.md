# Erdős #890 ↔ #1093 — large-prime / deficiency accounting bridge

Author: Jared Wilder. Public release: 2026-09-11.

This is the compact mathematical statement of a larger #890/#1093 subject program. The full research chronology remains in the archive; this file records the surviving identities and reduction in ordinary mathematical form.

## Large-prime binomial identity

Let `ω_{>k}(m)` denote the number of distinct prime divisors of `m` that exceed `k`. Then

`Σ_{i=0}^{k-1} ω_{>k}(n+i) = ω_{>k}( C(n+k-1,k) )`.

Indeed,

`C(n+k-1,k) = n(n+1)...(n+k-1)/k!`,

no prime `p>k` divides `k!`, and such a prime can divide at most one member of a length-`k` interval.

## Deficiency / excess identity

Write

`n+i = a_i b_i`,

where every prime divisor of `a_i` is at most `k` and every prime divisor of `b_i` is greater than `k`. Put

`d = #{i : b_i=1}`

and

`E = Σ_{b_i>1}(ω(b_i)-1)`.

Then

`Σ_i ω(b_i) = (k-d)+E`,

so

`Σ_i ω(b_i) <= k` if and only if `E<=d`.

Thus every `k`-smooth position supplies one unit of deficiency budget, while every additional distinct large prime beyond the first spends one unit.

## Erdős #1093 divisor-window reduction

Let `L_k=lcm(1,...,k)`. Under the #1093 admissibility condition, a `k`-smooth entry in the relevant length-`k` window must divide `L_k`. Therefore the deficiency can be written as

`δ(n,k) = #{ d | L_k : n-k < d <= n }`.

The admissibility hypothesis is essential here; the implication “`k`-smooth implies divides `L_k`” is not a statement about arbitrary integers.

This converts fixed-`k` positive deficiency into finite divisor geometry inside `L_k`.

## Finite computation

The accompanying divisor enumeration reproduced every then-recorded deficiency `>1` example through `k<=45`, including

`δ(284,28)=9`,

and found no additional examples in that scanned range.

That computation establishes the stated finite range. The structural identities and divisor-window reduction are the reusable mathematics.

## Repository status

The #890/#1093 material is already large enough to deserve a dedicated subject repository when repository creation is available. Until then, this compact theorem statement is the preferred reading surface; the intake archive preserves the full forensic chronology.
