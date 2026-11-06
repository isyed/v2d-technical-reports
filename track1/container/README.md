# Track 1: final container handoff

**Status: Episodes 9/12 completed fresh GPU execution and CPU review.

Material numerical variation and the full handoff remain unresolved.**

The runtime foundation passed an independent pinned download/hash check, OCI and
loaded-image identity checks, all **24 official stored-output checks**, and both
offline model-runtime imports. [Validation receipt](VALIDATION_RECEIPT.json).

The Docker startup repair also passed on the exact NGC image before the successful
GPU run. [CPU startup receipt](CPU_STARTUP_PREFLIGHT_RECEIPT.json).

Fresh inference completed for **Episodes 11 and 29** on November 6 at 12:07 a.m.

EST.

Those earlier pilot VMs and disks are confirmed deleted.

A separate approved
Episodes9/12 pilot subsequently completed on an L4 in `us-central1-a` at
**November6,2:54:49a.m.EST**.

Its controller, worker and boot disks are now confirmed
deleted.

There is no active Track1pilot cloud job.

The pilot reused frozen RGB-derived mesh priors and did not rerun mesh generation.

It covered two independent sequences, compared across four historical profiles.

The completed CPU review decoded the native human geometry.

On scored frames,
mean corresponding human-vertex differences are **1.27 mm / 2.37 mm** for Episodes
11/29.

The root-angle wrap has negligible geometric effect.

T1-11's object-vertex
differences average **0.23 cm / 0.51 cm**, with maxima **2.86 cm / 2.79 cm**.

These are differences from historical exports, **not competition scores**.
[Geometry evidence](CPU_GEOMETRY_REVIEW.json), [pilot review](FRESH_VIDEO_PILOT_REVIEW.json).

**T1-02's Episode 29 still has a material variation:** maximum object rotation
12.72 degrees and corresponding-vertex displacement 11.68 cm.

The larger variation
occurs on its nonlinear post-fit path.

The precise cause is unresolved because
the completed pilot omitted fresh pre-correction intermediates from its backup.

The tooling now retains compact stage evidence for subsequent tests.

The Episodes9/12 tracking pilot completed19stages with no training or competition
upload.

On scored frames, the T1-11 object-position differences average
**0.14cm / 0.78cm**.

Mean rotations differ **0.31degrees / 4.34degrees**; Episode12's
maximum is **25.96degrees**, a material gap already present before correction.

At its peak frame219, fresh visible-mask IoU is0.879versus0.790for the historical
pose.

The pan handle is partly hidden.

This source-only evidence supports pose
ambiguity but does not certify3Daccuracy or equivalent leaderboard scores.

Decoded human differences average **2.10mm / 1.84mm**.

These are reproduction
differences, **not competition scores**. [Completed pilot review](FRESH_TRACKING_PILOT_REVIEW.json),
[geometry](FRESH_TRACKING_GEOMETRY_REVIEW.json),
[source-only diagnosis](EPISODE12_SOURCE_VARIATION.json).

Maximum
recorded temperature was81C; no thermal pauses occurred.

Its evidence is backed up; no new cloud run was launched during review.

All **30base reconstruction paths are now prepared**, including the special3/16
workflows.

A563KBsource-only snapshot in the private repository removes the
dependency on an old local Docker tag for preparing the legacy code.

Episode3 preserves the original legacy optimizer behavior and requires
an explicit longer runtime: its historical refinement alone took about7hours.

**35tests and24native CPU startup/namespace checks pass.** These checks do not
certify GPU execution of the two special paths.

The11later-profile correction
cases remain unported, so T1-10/T1-11coverage remains19episodes.

Unsupported
profile selections fail before inference.

[Latest private adapter code](https://github.com/isyed/v2d-reconstruction/commit/4eddf61).

**Next:** finish the remaining profile corrections and numerical review, validate
the special workflows with an appropriate resource plan, then package the final
entry point and organizer-accessible archive.

The existing archive is a verified
foundation, not the complete handoff. [Adapter evidence](FRESH_TRACKING_ADAPTER.json).

This is the stable handoff page supplied with the technical-report form.

Archive identity and validation status are recorded below; an organizer-accessible download link and complete reproduction evidence remain pending.

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

All four covered profiles now pass the official checks inside Docker with networking disabled and a read-only filesystem: **24 passes, zero failures**.

Each retains its original submitted file, producing Git commit and 30 stored reconstructions.

A separate manifest is used for each producing commit; the official verifier is unchanged.

| Profile | Producing commit | Metric-wise best coverage | Relevant Kaggle IDs |
|---|---|---|---|
| T1-02 | `9337b8d1550a69aeaca9c498f5e8a3ce8ab0544a` | CD-H (tied), ACC-O, PEN | 57412915, 57412927, 57412931 |
| T1-03 | `4054ffdf78b1ab0658c8e949d216089bd9a138d6` | CD-H (tied) | 57416248 |
| T1-10 | `1529ad1af98aa4409e8a8d859cc2ee6654f9eca9` | ACC-H | 57547067 |
| T1-11 | `8eb8b6346f3150edfb84b20c1d039b148697ce7a` | CD-O; designated in the report form | 57605528 |

Packing uses the exact verified Python/NumPy environment separately from the original inference environment.

This avoids a module-name collision and mesh-packing differences caused by runtime dependencies.

No original submission, commit or verifier was changed.

These are stored-output checks.

The runtime and model bundle has now been built and uploaded to private project storage as a **49,008,771,072-byte OCI image archive**.

Its uploader-computed SHA-256 matches the finalized object's custom metadata.

A separate worker has now downloaded the pinned generation and recomputed that SHA-256 successfully.

The loaded-image identity, all 24 official checks and both offline runtime imports have also passed.

The development adapter genuinely reruns segmentation, depth/body/object motion,
CoCoNet, refinement, export and the historical correction recipes for Episodes
11/29.

It does not feed stored final trajectories into inference.

The remaining
historical tracking and correction branches require their own portable adapters.

The original artifact-check entry point continues to refuse unsupported raw-video
reproduction.

Counted files, producing commits and the official verifier remain
unchanged.

See [verification status](CPU_VERIFICATION.json),
[direct-export validation](DIRECT_EXPORT_VALIDATION.json) and
[archive status](ARCHIVE_STATUS.json).

## Organizer access

The implementation repository is private, with an invitation already issued to `Nvidia-V2D-Challenge`.

Large artifacts and pretrained assets will be shared with the organizers without changing third-party licenses.

This public page contains only documentation and non-secret provenance.

The preserved foundation archive exists, with its digest in [archive status](ARCHIVE_STATUS.json).

It is not yet certified as the complete raw-video handoff.

## Kaggle final-selection check

A subsequent authenticated read-only query using Kaggle’s selected-submission filter returned no explicit selected entries on the relevant boards.

The IDs above are the files designated in the recorded Google form; this does not establish that they are manually selected on Kaggle.

No Kaggle selections were changed.

Track 1’s metric-wise best scores come from different historical files.

The form designates T1-11 consistently across the five metrics.

The current kit permits a separate manifest entry for every file that counts on a metric board.

Container coverage must therefore include the metric-wise best files if no manual selection exists; this does not require resubmitting the Google form.

A recorded report form does not itself change Kaggle selection.

## Official kit

The ZIP linked from the official competition page was downloaded again on November 4 at 7:01 p.m.

EST.

Its SHA-256 is `7e1fdd00b50189191b4f1bf03158607f4f1a7bb5bfb0bf867b14eb06270a77f0`.

The checks above use its unmodified verifier.

No complete handoff archive or raw-video reproduction result is claimed.
