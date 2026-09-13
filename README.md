# Erdős #1192: representation energy of additive bases

Can an asymptotic basis of order `r` have linear total squared representation
count? For a set `A` of positive integers, define

```text
f_r(n) = number of ordered r-tuples from A whose sum is n (repetitions allowed)
E_r(x) = sum_{0 ≤ n ≤ x} f_r(n)^2
M(y)   = |A ∩ [1,y]|.
```

The campaign seeks a basis with `E_r(x)=O(x)`. This repository organizes
Jared Wilder's corrected supporting inequalities and original exploration.
It supplies no general `r≥3` construction or refutation, and claims no novelty
for its elementary Cauchy–Schwarz consequences.

## Start with the corrected proof

The [proof note](research/erdos-1192-energy-floor-and-density-ceiling.md)
gives two unconditional estimates:

1. If every integer `n≥N` is represented, then for integer `x≥N`,
   `E_r(x) ≥ (x−N+1)²/(x+1)`.
2. For integer `y≥1`, `E_r(ry) ≥ M(y)^(2r)/(ry+1)`.

For the first estimate, at least `x−N+1` tuples contribute; apply
Cauchy–Schwarz to the `x+1` representation counts. For the second, all
`M(y)^r` tuples have sums at most `ry`, and the same inequality applies.

Consequently linear energy forces `M(y)=O(y^(1/r))`. The basis property
forces the matching lower order `M(x)≥(x−N+1)^(1/r)`. Any successful
positive-integer basis therefore sits at this density scale. If allowing
zero in `A`, count `A∩[0,x]` instead for the exact lower inequality;
the asymptotic scale is unchanged.

## Corrections and research history

The correct cutoff for tuples from `A∩[1,2^k]` is **`r·2^k`**. A previous
route incorrectly put all their sums in the smaller `2^k` window. The repaired
inequality and its explanation are in the proof note. An imported `r=2`
result was also retracted as a proposed closure of the general target;
historical route labels do not override these corrections.

| Read | Purpose |
|---|---|
| [Corrected proof note](research/erdos-1192-energy-floor-and-density-ceiling.md) | Mathematical entry point and exact repaired inequalities |
| [Campaign contract](research/campaign/contract.json) | Original definitions, target and scope |
| [Results](research/campaign/results.json) / [route registry](research/campaign/routes/registry.jsonl) | Dated route outcomes, including rejected arguments |
| [Campaign log](research/campaign/campaign-log.json) / [transcript](research/campaign/transcript.jsonl) | Full historical development; not a theorem ledger |
| [Transfer evidence](research/campaign/transfer-evidence.json) | Recorded provenance |

## Verification and provenance

```sh
python verification/verify_source.py
```

This checks source bytes, SHA-256 hashes and Git blob IDs. There is no Lean
source in this campaign and no Lean-build claim. Mathematical authority for
the supporting inequalities is the written proof, separate from file integrity.
Literature statements in the original note are preserved as source assertions;
this release is an organizational recovery, not a new priority audit.

[SOURCE-MANIFEST.json](SOURCE-MANIFEST.json) pins all six campaign artifacts
from the [campaign archive](https://github.com/jaredwilder/erdos-campaign-archive)
and the corrected note from the
[findings ledger](https://github.com/jaredwilder/erdos-findings-ledger).
All seven research sources are copied exactly. Both original license records
are preserved; see [LICENSE](LICENSE) and
[the ledger license](research/source-metadata/LICENSE-erdos-findings-ledger).

Author: Jared Wilder. Focused release: 2026-09-13. License: Apache-2.0.
