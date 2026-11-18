# Track 2 container handoff

Team longbot · Updated November 17, 2026

**Container pending.** This is the handoff URL recorded in the Track 2 form. No complete Track 2 image or archive is available for download. Kaggle confirmed that all 12 submission IDs recorded in the form were scored. [Track 2 technical report](../report.pdf)

## Submitted artifacts

| Tier | Form designation | Exact submitted CSV | Matching policy files | Producing source |
| --- | --- | --- | ---: | --- |
| 1 | Submission 7 | Recovered | 30/30 | [`b9d486f`](https://github.com/isyed/v2d-grounding/commit/b9d486f2bc93f6448fdf719406d4162ce460879f) |
| 2 | Submission 2 | Recovered | 30/30 | [`706a0c9`](https://github.com/isyed/v2d-grounding/commit/706a0c9c5422e3ee899197e24c6edce8c2b71c4d) |
| 3 | Submission 4 | Recovered | 0/30 | [`43ef31a`](https://github.com/isyed/v2d-grounding/commit/43ef31abbc0666736a5bf692b148a1cc947f03ca) |

The original Tier 3 policy bundle and its scene and frame references are still missing. The CSV preserves the submitted trajectories and expected policy hashes. The organizer account `Nvidia-V2D-Challenge` has access to the [private source repository](https://github.com/isyed/v2d-grounding).

## Evaluator verification

The current official verifier reports nine passes, one evaluator code hash failure and one skipped repack check for each of the recovered Tiers 1 and 2. These checks ran on the host CPU. The historical evaluator code hashes additional runtime files, and the original source reproduces the submitted digest. The current verifier hashes four FlashCHORD evaluation files and produces a different digest.

| Tiers | Recorded and recomputed historical SHA-256 | Current verifier SHA-256 |
| --- | --- | --- |
| 1 and 2 | `b1f208ba73f17e73dd5a6bc62d0a139b25ebe28e33ff2d84fa49dbf395936b80` | `a3d3dfcc42c98ba76effe0413573cc824953090e3ca02faf580c311aa748a8bb` |

The submitted CSVs and the official verifier remain unchanged. We need an organizer decision on the historical hash and whether a partial Tier 1 and 2 handoff is acceptable if the exact Tier 3 artifacts cannot be recovered. Offline image verification and fresh GPU reproduction remain pending.
