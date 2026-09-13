# Erdős #1093 — divisor-window reduction, with an Erdős #890 bridge

**Estate source:** MSL Pass-3 audited release  
**Status:** exact reduction + finite computation + cross-problem identity; **neither #1093 nor #890 is declared closed**

## 1. Exact admissibility hypothesis

For the #1093 campaign, a pair `(n,k)` is **admissible** when

\[
\boxed{p\nmid\binom nk\quad\text{for every prime }p\le k.}
\]

The problem's deficiency counts those `i`, `0<=i<k`, for which `n-i` is `k`-smooth.

Let

\[
L_k=\operatorname{lcm}(1,2,\ldots,k).
\]

## 2. The divisor-window theorem

For an admissible `(n,k)` and `0<=i<k`,

\[
\boxed{
 n-i\text{ is }k\text{-smooth}
 \iff
 n-i\mid L_k.
}
\]

### Nontrivial direction

Suppose `n-i` is `k`-smooth but has a prime-power divisor

\[
p^a\mid n-i
\]

with `p^a>k`. Then

\[
n\equiv i\pmod{p^a}.
\]

Since

\[
i<k<p^a,
\]

the base-`p` digits of `k` cannot all be bounded above by the corresponding digits of `i`; otherwise `k<=i`. Because the lowest `a` base-`p` digits of `n` agree with those of `i`, some base-`p` digit of `k` exceeds the corresponding digit of `n`.

Lucas' theorem then gives

\[
p\mid\binom nk,
\]

contradicting admissibility.

Therefore every prime-power component of the `k`-smooth integer `n-i` is at most `k`, and hence divides `L_k`. So `n-i|L_k`.

The reverse direction is immediate: every divisor of `L_k` has no prime factor exceeding `k`.

## 3. Exact deficiency formula

Consequently

\[
\boxed{
\delta(n,k)
=
\#\{d\mid L_k:n-k<d\le n\}.
}
\]

Immediate consequences are

\[
\delta(n,k)>0
\Longrightarrow
n\le L_k+k-1,
\]

and every positive-deficiency candidate has the form

\[
\boxed{
n=d+i,
\qquad d\mid L_k,
\qquad 0\le i<k.
}
\]

Thus for each fixed `k`, the positive-deficiency search is an **exact finite divisor problem**, not an unbounded search over `n`.

## 4. Exact computation through `k<=45`

The source estate implemented the divisor enumeration above through `k=45`. Its comparison audit records the following deficiency-`>1` cases in that range:

- `delta(44,8)=2`;
- `delta(46,10)=3`;
- `delta(47,10)=3`;
- `delta(74,10)=2`;
- `delta(47,11)=4`;
- `delta(174,12)=2`;
- `delta(239,14)=2`;
- `delta(241,16)=3`;
- `delta(2105,25)=3`;
- `delta(1119,27)=3`;
- `delta(5179,27)=2`;
- `delta(284,28)=9`;
- `delta(8413,28)=2`;
- `delta(8414,28)=2`;
- `delta(6459,33)=3`;
- `delta(96622,42)=2`.

The finite engine found no other deficiency-`>1` pairs through the stated `k<=45` frontier.

**Scope:** exact computation in that finite range only. The release does not infer an all-`k` classification from it.

## 5. Erdős #890 — large-prime binomial identity

Define `omega_k(m)` to count the distinct prime divisors of `m` that are greater than `k`; equivalently write `omega_{>k}` when the threshold is displayed explicitly.

A prime `p>k` cannot divide two distinct members of a length-`k` interval. If

\[
p\mid n+i,
\qquad
p\mid n+j,
\qquad i\ne j,
\]

then `p|(j-i)`, impossible because

\[
0<|j-i|<k<p.
\]

Using

\[
n(n+1)\cdots(n+k-1)
=
k!\binom{n+k-1}{k}
\]

and the fact that `k!` has no prime divisor exceeding `k`, one gets the exact identity

\[
\boxed{
\sum_{i=0}^{k-1}\omega_k(n+i)
=
\omega_{>k}\!\binom{n+k-1}{k}.
}
\]

Thus the corresponding #890 quantity is exactly a large-distinct-prime-factor count for one binomial coefficient.

## 6. #890 ↔ #1093 deficiency/excess accounting

At an admissible #1093 window, factor each `n+i` as

\[
n+i=a_i b_i,
\]

where `a_i` is the `k`-smooth part and `b_i` contains only primes `>k`.

Let

\[
d=\#\{i:b_i=1\}
\]

be the deficiency contribution, and let

\[
E=
\sum_{b_i>1}(\omega(b_i)-1)
\]

count the extra large-prime factors beyond one per non-smooth member.

If

\[
S_k=\sum_{i=0}^{k-1}\omega_k(n+i),
\]

then every `b_i=1` contributes zero, while every other `b_i` contributes one baseline large prime plus its excess. Hence

\[
\boxed{S_k=k-d+E.}
\]

Therefore

\[
\boxed{S_k\le k\iff E\le d.}
\]

In words: **#1093 deficiency pays for #890 excess large-prime complexity.**

This is a structural bridge between the two campaigns. It is not itself a solution of either problem.

## 7. Novelty and formalization boundary

The source audit explicitly left historical novelty of the `L_k` divisor-window formulation unresolved. The proof is released because it is mathematically explicit and falsifiable, not because this repository claims priority over all earlier Lucas/Kummer/divisor-window literature.

The natural formalization program is:

1. state admissibility exactly as `forall p<=k, Prime p -> p ∤ choose n k`;
2. formalize the Lucas digit contradiction for a prime-power divisor `p^a>k` of `n-i`;
3. deduce `n-i|lcm(1,...,k)`;
4. identify the deficiency Finset with divisors of `L_k` in `(n-k,n]`;
5. separately formalize the #890 prime-separation/product identity.

The finite `k<=45` engine should remain a separate exact-computation receipt rather than being mixed into the universal proof.