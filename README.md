# Erdős #890 / #1093 — divisor-window bridge

A structural reduction connecting two binomial/divisor problems through an exact divisor-window theorem and a large-prime factor identity.

## Divisor-window theorem for #1093

Call `(n,k)` admissible when

\[
p\nmid {n\choose k}\qquad\text{for every prime }p\le k.
\]

Let

\[
L_k=\operatorname{lcm}(1,2,\ldots,k).
\]

For every admissible `(n,k)` and every `0\le i<k`, the program proves

\[
\boxed{
n-i\text{ is }k\text{-smooth}
\iff
n-i\mid L_k.
}
\]

Hence the deficiency is exactly

\[
\boxed{
\delta(n,k)=\#\{d\mid L_k:n-k<d\le n\}.
}
\]

In particular, positive deficiency forces

\[
n\le L_k+k-1,
\]

and every positive-deficiency candidate has the finite form `n=d+i` with `d|L_k` and `0<=i<k`.

The proof uses Lucas' theorem: a `k`-smooth `n-i` containing a prime power `p^a>k` would force `p | C(n,k)`, contradicting admissibility.

## Exact finite frontier

The divisor engine exhausts the resulting finite search through `k<=45`. Among its deficiency-`>1` cases are

```text
δ(44,8)=2       δ(46,10)=3      δ(47,10)=3
δ(47,11)=4      δ(284,28)=9     δ(96622,42)=2
```

with the complete list in [`divisor-window/README.md`](divisor-window/README.md).

## Large-prime identity for #890

Let `ω_k(m)` count distinct prime divisors of `m` larger than `k`. A prime `p>k` cannot divide two different terms in a block of `k` consecutive integers, so

\[
\boxed{
\sum_{i=0}^{k-1}\omega_k(n+i)
=
\omega_{>k}\!\left({n+k-1\choose k}\right).
}
\]

Thus the #890 quantity is exactly the number of distinct prime factors larger than `k` in one binomial coefficient.

For an admissible #1093 window, write each `n+i=a_i b_i`, with `a_i` `k`-smooth and all prime factors of `b_i` larger than `k`. If `d` counts the indices with `b_i=1` and

\[
E=\sum_{b_i>1}(\omega(b_i)-1),
\]

then

\[
\boxed{S_k=k-d+E}.
\]

Equivalently,

\[
S_k\le k\iff E\le d.
\]

This is the bridge: #1093 deficiency exactly pays for excess large-prime complexity in #890.

## Layout

- [`divisor-window/`](divisor-window) — theorem, proof, finite frontier, and #890 bridge.
- [`bridge/`](bridge) — broader extraction and computational material.
- [`compact/`](compact) — compact theorem mirrors.

The reductions and finite frontier above are exact; neither parent problem is claimed solved.

Author: Jared Wilder.
