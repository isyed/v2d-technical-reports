# Track 1: final container handoff

**Status: container upload and end-to-end validation pending.**

This is the stable handoff page supplied with the technical-report form. It is not yet a downloadable, verified container. Download URLs, image identity, archive SHA-256 and reproduction results will be added here after packaging and verification.

Team: longbot.

## Selected files

### Track 1 T1-11

Producing code: https://github.com/isyed/v2d-reconstruction/commit/8eb8b6346f3150edfb84b20c1d039b148697ce7a

Exact submitted-file SHA-256: `395e4d7c6f001bcdc4472a92e9d6022c89d791499dfa64d6576eed82b33fc07a`

- cd_h_cm: Kaggle ID **57605527**, score **15.47123** ([board](https://www.kaggle.com/competitions/v2d-challenge-track1-cd-h)).
- cd_o_cm: Kaggle ID **57605528**, score **24.21106** ([board](https://www.kaggle.com/competitions/v2d-challenge-track1-cd-o)).
- acc_h_cm: Kaggle ID **57605530**, score **0.27484** ([board](https://www.kaggle.com/competitions/v2d-challenge-track1-acc-h)).
- acc_o_cm: Kaggle ID **57605533**, score **0.49967** ([board](https://www.kaggle.com/competitions/v2d-challenge-track1-acc-o)).
- interpenetration_cm: Kaggle ID **57605538**, score **0.00485** ([board](https://www.kaggle.com/competitions/v2d-challenge-track1-pen)).

## Verification scope

The exact submitted Parquet and producing commit are preserved. Host CPU verification of the staged directory passes all six checks, including repacking all 30 stored episode reconstructions with the retained Episode 8 update to match the submitted file. This is stored-output verification, not raw-video reproduction. Fresh raw-video reconstruction, model bundling, the Docker runtime check and sampled GPU reruns remain incomplete. See [CPU verification status](CPU_VERIFICATION.json).

## Organizer access

The implementation repository is private, with an invitation already issued to `Nvidia-V2D-Challenge`. Large artifacts and pretrained assets will be shared with the organizers without changing third-party licenses. This public page contains only documentation and non-secret provenance.

No final archive digest or download URL is listed until the artifact actually exists.

## Kaggle final-selection check

A subsequent authenticated read-only query using Kaggle’s selected-submission filter returned no explicit selected entries on the relevant boards. The IDs above are the files designated in the recorded Google form; this does not establish that they are manually selected on Kaggle. No Kaggle selections were changed. Track 1’s metric-wise best scores come from different historical files. The form designates T1-11 consistently across the five metrics. Final-selection or organizer confirmation remains necessary; a recorded report form does not itself change Kaggle selection.
