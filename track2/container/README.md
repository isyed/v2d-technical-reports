# Track 2: final container handoff

**Status: container upload and end-to-end validation pending.**

This is the stable handoff page supplied with the technical-report form. It is not yet a downloadable, verified container. Download URLs, image identity, archive SHA-256 and reproduction results will be added here after packaging and verification.

Team: longbot.

## Selected files

### Track 2 Tier 1 S7

Producing code: https://github.com/isyed/v2d-grounding/commit/b9d486f2bc93f6448fdf719406d4162ce460879f

Exact submitted-file SHA-256: `b31d394123012a9f6b91135de657cb51fbcd75d82c03b068381760da4564c58b`

- add_auc: Kaggle ID **57690247**, score **0.32917** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier1-auc)).
- spider_sr: Kaggle ID **57690303**, score **0.13333** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier1-sp-sr)).
- maniptrans_sr: Kaggle ID **57690341**, score **0.13333** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier1-mp-sr)).
- mppe_cm: Kaggle ID **57690370**, score **39.21800** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier1-mppe)).

### Track 2 Tier 2 S2

Producing code: https://github.com/isyed/v2d-grounding/commit/706a0c9

Exact submitted-file SHA-256: `7a1cbeb1947cc5adaa86b8518f55a4d54135fbc07e8bd11ade22748be5431153`

- add_auc: Kaggle ID **57749110**, score **0.25073** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier2-auc)).
- spider_sr: Kaggle ID **57749114**, score **0.03333** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier2-sp-sr)).
- maniptrans_sr: Kaggle ID **57749116**, score **0.03333** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier2-mp-sr)).
- mppe_cm: Kaggle ID **57749117**, score **55.10178** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier2-mppe)).

### Track 2 Tier 3 S4

Producing code: https://github.com/isyed/v2d-grounding/commit/43ef31abbc0666736a5bf692b148a1cc947f03ca

Exact submitted-file SHA-256: `2527e2a0565b268a5bf3c55db9323f46ca655e56ab274c66b7dccd10d74e4f95`

- add_auc: Kaggle ID **57998366**, score **0.19051** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier3-auc)).
- spider_sr: Kaggle ID **57998372**, score **0.00000** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier3-sp-sr)).
- maniptrans_sr: Kaggle ID **57998378**, score **0.00000** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier3-mp-sr)).
- mppe_cm: Kaggle ID **57998382**, score **59.96399** ([board](https://www.kaggle.com/competitions/v2d-challenge-track2-tier3-mppe)).

## Provenance compatibility disclosure

All 90 selected policy/checkpoint files match the hashes in the submitted CSVs. The original producing commits are available as clean independent checkouts. The original evaluator scripts and broader source-hash functions reproduce the recorded identities exactly for all three tiers.

The newly downloaded official container verifier computes `eval_code_sha256` from only four FlashCHORD evaluation files. Our historical submission adapters instead hashed the broader execution implementation, including controller and scene code. Therefore the official four-file comparison differs even though the original broader digest matches. No submitted provenance, checkpoint, runtime source or official verifier has been rewritten. Organizer confirmation is required on this historical hash-contract difference.

| Tier | Recorded/original broader hash | Official four-file recomputation |
|---|---|---|
| tier1 | `b1f208ba73f17e73dd5a6bc62d0a139b25ebe28e33ff2d84fa49dbf395936b80` | `a3d3dfcc42c98ba76effe0413573cc824953090e3ca02faf580c311aa748a8bb` |
| tier2 | `b1f208ba73f17e73dd5a6bc62d0a139b25ebe28e33ff2d84fa49dbf395936b80` | `a3d3dfcc42c98ba76effe0413573cc824953090e3ca02faf580c311aa748a8bb` |
| tier3 | `c7a561caf4c3e62cbddc5170d00a724ac725767018afe332627a4182b2f04d12` | `fe0acf9309e63136edf292ebd67ed988ccae081827fcb4248e150fa594c51191` |

The original `eval_script_sha256` also matches for every tier. The Tier 3 entry identifies the original `evaluation_build.py` provenance adapter; it is not renamed to masquerade as the upstream evaluator. Host CPU verification of each staged tier directory reports 10 passes and one failure: the disclosed evaluator source-hash contract. Repacking the stored rollouts matches every submitted file. These are not Docker or GPU reproduction tests. See [CPU verification status](CPU_VERIFICATION.json). GPU reproduction and the offline runtime packaging check are not yet complete.

## Organizer access

The implementation repository is private, with an invitation already issued to `Nvidia-V2D-Challenge`. Large artifacts and pretrained assets will be shared with the organizers without changing third-party licenses. This public page contains only documentation and non-secret provenance.

No final archive digest or download URL is listed until the artifact actually exists.

## Kaggle final-selection check

A subsequent authenticated read-only query using Kaggle’s selected-submission filter returned no explicit selected entries on the relevant boards. The IDs above are the files designated in the recorded Google form; this does not establish that they are manually selected on Kaggle. No Kaggle selections were changed. The designated Track 2 files attain the best available public scores for their tiers, including ties on some success-rate boards.

## Fresh official-kit check, November 4, 2026

The ZIP linked from the official competition page was downloaded again at 7:01 p.m. EST. It is identical to the earlier download (SHA-256 `7e1fdd00b50189191b4f1bf03158607f4f1a7bb5bfb0bf867b14eb06270a77f0`; server Last-Modified November 2). The untouched fresh verifier was rerun against the staged directories. Each Track 2 tier retains ten passes and the same single evaluator code-hash failure. Original broader hashes were recomputed again and still match the submitted values exactly. These are host CPU checks, not completed Docker/GPU reproduction. No completed container archive is available yet.
