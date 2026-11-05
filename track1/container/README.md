# Track 1: final container handoff

**Status: runtime archive uploaded privately; validation and complete handoff pending.**

Latest cloud snapshot: the 49.0 GB runtime foundation archive was uploaded on November 5 at 4:05 p.m. EST. The worker stopped on a receipt-parsing bug after upload; the archive is preserved, and the VM and disk are deleted. Independent archive/runtime validation is next.


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

These are stored-output checks. The runtime and model bundle has now been built and uploaded to private project storage as a **49,008,771,072-byte OCI image archive**. Its uploader-computed SHA-256 matches the finalized object's custom metadata. This is upload evidence; independent download/hash verification and offline runtime validation of this archive have not run yet.

The worker stopped because the receipt checker expected the raw API's `metadata` field, while `gcloud` reports it as `custom_fields`. The parser is corrected and tested, and a recovered receipt is saved with validation explicitly pending. No new worker is running. The next worker can load and validate the preserved archive without rebuilding it.

The historical raw-video reproduction adapter and sampled GPU reruns remain unfinished. The artifact-check entry point continues to refuse raw-video reproduction until a real pipeline is supplied. Full competition handoff requires those checks and an organizer-accessible final archive link. See [verification status](CPU_VERIFICATION.json), [direct-export validation](DIRECT_EXPORT_VALIDATION.json) and [archive status](ARCHIVE_STATUS.json).

## Organizer access

The implementation repository is private, with an invitation already issued to `Nvidia-V2D-Challenge`. Large artifacts and pretrained assets will be shared with the organizers without changing third-party licenses. This public page contains only documentation and non-secret provenance.

No final archive digest or download URL is listed until the artifact actually exists.

## Kaggle final-selection check

A subsequent authenticated read-only query using Kaggle’s selected-submission filter returned no explicit selected entries on the relevant boards. The IDs above are the files designated in the recorded Google form; this does not establish that they are manually selected on Kaggle. No Kaggle selections were changed. Track 1’s metric-wise best scores come from different historical files. The form designates T1-11 consistently across the five metrics. The current kit permits a separate manifest entry for every file that counts on a metric board. Container coverage must therefore include the metric-wise best files if no manual selection exists; this does not require resubmitting the Google form. A recorded report form does not itself change Kaggle selection.

## Official kit

The ZIP linked from the official competition page was downloaded again on November 4 at 7:01 p.m. EST. Its SHA-256 is `7e1fdd00b50189191b4f1bf03158607f4f1a7bb5bfb0bf867b14eb06270a77f0`. The checks above use its unmodified verifier. No complete handoff archive or raw-video reproduction result is claimed.
