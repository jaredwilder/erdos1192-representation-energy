# Erdős #1192 — Representation Energy of Additive Bases

**Jared Wilder**

Energy bounds and density constraints for additive bases of order `r`.

For a set `A` of positive integers, define

```text
f_r(n) = number of ordered r-tuples from A whose sum is n
E_r(x) = sum_{0 ≤ n ≤ x} f_r(n)^2
M(y)   = |A ∩ [1,y]|.
```

The target is an asymptotic basis of order `r` with `E_r(x)=O(x)`.

## Two basic inequalities

The [proof note](research/erdos-1192-energy-floor-and-density-ceiling.md) establishes:

1. If every integer `n ≥ N` is represented, then for integer `x ≥ N`,

   ```text
   E_r(x) ≥ (x−N+1)^2/(x+1).
   ```

2. For integer `y ≥ 1`,

   ```text
   E_r(ry) ≥ M(y)^(2r)/(ry+1).
   ```

Both follow from Cauchy–Schwarz applied to the relevant representation counts.

## Density consequence

Linear representation energy forces

```text
M(y) = O(y^(1/r)).
```

The basis property gives the matching lower order

```text
M(x) ≥ (x−N+1)^(1/r).
```

Thus any positive solution must live at the natural density scale

```text
M(x) = Θ(x^(1/r))
```

up to constants.

## Corrected cutoff

For tuples drawn from `A ∩ [1,2^k]`, the correct sum range is

```text
[0, r·2^k],
```

not `[0,2^k]`. The proof note contains the repaired inequality and the resulting density argument.

## Repository map

- [Corrected proof note](research/erdos-1192-energy-floor-and-density-ceiling.md) — mathematical entry point
- `research/campaign/` — route exploration, logs, and recorded outcomes
- `SOURCE-MANIFEST.json` — exact provenance of the recovered source files
- `verification/verify_source.py` — source-integrity check

Run:

```sh
python verification/verify_source.py
```

The full `r ≥ 3` construction problem remains open; this repository isolates the energy floor and density scale that any successful construction must satisfy.

**License:** Apache-2.0