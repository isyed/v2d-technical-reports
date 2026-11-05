# Track 1: final container handoff

**Status: container upload and end-to-end validation pending.**

Latest cloud snapshot (November 5, 3:20 p.m. EST): all 12 build steps and layer compression are complete; the direct OCI archive is being written. The heartbeat reports 0.74 GiB written and 166 GiB free. Checkpoint upload and this worker’s validation are still pending.


This is the stable handoff page supplied with the technical-report form. It is not yet a downloadable, verified container. Download URLs, image identity, archive SHA-256 and reproduction results will be added here after packaging and verification.

Team: longbot. Contact: syedim@gmail.com.

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

All four covered profiles now pass the official checks inside Docker with networking disabled and a read-only filesystem: **24 passes, zero failures**. Each retains its original submitted file, producing Git commit and 30 stored reconstructions. A separate manifest is used for each producing commit; the official verifier is unchanged.

| Profile | Producing commit | Metric-wise best coverage | Relevant Kaggle IDs |
|---|---|---|---|
| T1-02 | `9337b8d1550a69aeaca9c498f5e8a3ce8ab0544a` | CD-H (tied), ACC-O, PEN | 57412915, 57412927, 57412931 |
| T1-03 | `4054ffdf78b1ab0658c8e949d216089bd9a138d6` | CD-H (tied) | 57416248 |
| T1-10 | `1529ad1af98aa4409e8a8d859cc2ee6654f9eca9` | ACC-H | 57547067 |
| T1-11 | `8eb8b6346f3150edfb84b20c1d039b148697ce7a` | CD-O; designated in the report form | 57605528 |

Packing uses the exact verified Python/NumPy environment separately from the original inference environment. This avoids a module-name collision and mesh-packing differences caused by runtime dependencies. No original submission, commit or verifier was changed.

These are stored-output checks. Full raw-video model/runtime bundling, the reproduction adapter and sampled GPU reruns remain unfinished. The existing artifact-check image deliberately refuses raw-video reproduction rather than replaying stored outputs. After the previous daemon-based checkpoint export timed out, direct OCI archive export was tested locally on the existing 15.8 GiB artifact-check image. Export, Docker reload, identical filesystem layers/runtime settings and all 24 official checks passed in about eight minutes. This validates the archive path at that size, not the all-model runtime foundation. A new independent CPU worker started November 5 at 2:31 p.m. EST, using direct archive creation and private backup before Docker loading/validation, the original SAM3D environment setting, and a three-hour automatic deletion limit. The original $8 total campaign ceiling includes all three prior stopped attempts. No final container download is claimed until its archive exists and required reproduction checks are complete. Raw-video reproduction remains unfinished. See [verification status](CPU_VERIFICATION.json) and [direct-export validation](DIRECT_EXPORT_VALIDATION.json).

## Organizer access

The implementation repository is private, with an invitation already issued to `Nvidia-V2D-Challenge`. Large artifacts and pretrained assets will be shared with the organizers without changing third-party licenses. This public page contains only documentation and non-secret provenance.

No final archive digest or download URL is listed until the artifact actually exists.

## Kaggle final-selection check

A subsequent authenticated read-only query using Kaggle’s selected-submission filter returned no explicit selected entries on the relevant boards. The IDs above are the files designated in the recorded Google form; this does not establish that they are manually selected on Kaggle. No Kaggle selections were changed. Track 1’s metric-wise best scores come from different historical files. The form designates T1-11 consistently across the five metrics. The current kit permits a separate manifest entry for every file that counts on a metric board. Container coverage must therefore include the metric-wise best files if no manual selection exists; this does not require resubmitting the Google form. A recorded report form does not itself change Kaggle selection.

## Official kit

The ZIP linked from the official competition page was downloaded again on November 4 at 7:01 p.m. EST. Its SHA-256 is `7e1fdd00b50189191b4f1bf03158607f4f1a7bb5bfb0bf867b14eb06270a77f0`. The checks above use its unmodified verifier. No complete handoff archive or raw-video reproduction result is claimed.
