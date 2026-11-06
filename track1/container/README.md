# Track 1: final container handoff

**Status: fresh-video pilot completed; numerical/geometry review and the complete handoff remain pending.**

The separate CPU validation passed on November 5: archive download/SHA-256, OCI identity, loaded filesystem/runtime settings, all **24 official checks**, and both SAM2/SAM3D offline imports. The worker then requested automatic deletion. [Validation receipt](VALIDATION_RECEIPT.json).

**CPU startup preflight passed on the exact NGC VM image** on November 5 at 9:40 p.m. EST. Docker restart, containerd image storage, preserved NVIDIA runtime settings, OCI import/layer identity and offline read-only container execution all passed. No GPU, model weights or videos were used. The receipt is backed up; the VM and its disk are confirmed deleted. [CPU startup receipt](CPU_STARTUP_PREFLIGHT_RECEIPT.json).

The cloud tests resolved two issues: the systemd service replacement must sort after NGC's vendor override, and untagged OCI imports should be addressed by their exact manifest digest. The suite now has **15 passing tests**. This verifies startup and CPU container execution; it does not verify GPU inference or fresh-video reproduction.

**The cloud pilot completed both Episodes 11 and 29** on November 6 at 12:07 a.m. EST. Results and logs are backed up; all pilot VMs and disks are confirmed deleted. There is no active cloud job.

Fresh exports match the frame counts, float32 data types and reused object mesh bytes, but are **not bit exact** to the historical submissions. On scoring-frame indices, T1-11's mean object-position differences are **0.15 cm / 0.44 cm** for Episodes 11/29; mean rotation differences are **0.24° / 0.55°**. T1-02's Episode 29 has a larger maximum rotation difference of **12.72°**, requiring review. These are differences from saved outputs, not competition scores. [Pilot review](FRESH_VIDEO_PILOT_REVIEW.json).

The largest raw human-pose delta is a root Euler-angle wrap near 2 pi, rather than a six-radian physical jump. Decoded human geometry and remaining numerical differences still need comparison. GPU thermal logs recorded a maximum **80°C**, a **60 W** limit and no thermal pauses. The total campaign ceiling stayed at $4; actual billed cost is not yet known.

**Next:** review decoded human/object geometry on CPU, investigate T1-02 Episode 29's orientation variation, then finish the remaining 28 episode recipes and the final raw-video entry point before completing container delivery. This pilot reused frozen RGB-derived mesh priors; it did not regenerate object meshes or implement all 30 episodes. No further cloud run has been launched.


This is the stable handoff page supplied with the technical-report form. Archive identity and validation status are recorded below; an organizer-accessible download link and complete reproduction evidence remain pending.

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

These are stored-output checks. The runtime and model bundle has now been built and uploaded to private project storage as a **49,008,771,072-byte OCI image archive**. Its uploader-computed SHA-256 matches the finalized object's custom metadata. A separate worker has now downloaded the pinned generation and recomputed that SHA-256 successfully. The loaded-image identity, all 24 official checks and both offline runtime imports have also passed.

The worker stopped because the receipt checker expected the raw API's `metadata` field, while `gcloud` reports it as `custom_fields`. The parser is corrected and tested, and a recovered receipt recorded validation as pending at that point. The validation-only worker checked the preserved archive successfully without rebuilding it. The original builder and disk remain deleted; the validator requested its own deletion after backing up evidence.

A development fresh-motion adapter has been prepared and CPU-checked for Episodes 11 and 29. It reruns segmentation, depth/body/object motion, CoCoNet, refinement and the historical correction recipes, using the original frozen image-derived category mesh priors. It contains no stored final trajectories as inference inputs. The comparison tool passes known 1 cm translation and 90-degree rotation tests. Its GPU execution, mesh regeneration and support for the other 28 episodes remain unverified; a separate bounded GPU pilot has now been authorized and its private payload uploaded. The historical all-30 raw-video reproduction adapter remains unfinished. The artifact-check entry point continues to refuse raw-video reproduction until a real pipeline is supplied. Full competition handoff requires those checks and an organizer-accessible final archive link. See [verification status](CPU_VERIFICATION.json), [direct-export validation](DIRECT_EXPORT_VALIDATION.json) and [archive status](ARCHIVE_STATUS.json).

## Organizer access

The implementation repository is private, with an invitation already issued to `Nvidia-V2D-Challenge`. Large artifacts and pretrained assets will be shared with the organizers without changing third-party licenses. This public page contains only documentation and non-secret provenance.

The preserved foundation archive exists, with its digest in [archive status](ARCHIVE_STATUS.json). It is not yet certified as the complete raw-video handoff.

## Kaggle final-selection check

A subsequent authenticated read-only query using Kaggle’s selected-submission filter returned no explicit selected entries on the relevant boards. The IDs above are the files designated in the recorded Google form; this does not establish that they are manually selected on Kaggle. No Kaggle selections were changed. Track 1’s metric-wise best scores come from different historical files. The form designates T1-11 consistently across the five metrics. The current kit permits a separate manifest entry for every file that counts on a metric board. Container coverage must therefore include the metric-wise best files if no manual selection exists; this does not require resubmitting the Google form. A recorded report form does not itself change Kaggle selection.

## Official kit

The ZIP linked from the official competition page was downloaded again on November 4 at 7:01 p.m. EST. Its SHA-256 is `7e1fdd00b50189191b4f1bf03158607f4f1a7bb5bfb0bf867b14eb06270a77f0`. The checks above use its unmodified verifier. No complete handoff archive or raw-video reproduction result is claimed.
