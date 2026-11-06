# Track 1: final container handoff

**Status: the new Episodes 9/12 tracking-reproduction pilot is queued; its independent controller is retrying L4 capacity.

Full raw-video handoff remains incomplete.**

The runtime foundation passed an independent pinned download/hash check, OCI and
loaded-image identity checks, all **24 official stored-output checks**, and both
offline model-runtime imports. [Validation receipt](VALIDATION_RECEIPT.json).

The Docker startup repair also passed on the exact NGC image before the successful
GPU run. [CPU startup receipt](CPU_STARTUP_PREFLIGHT_RECEIPT.json).

Fresh inference completed for **Episodes 11 and 29** on November 6 at 12:07 a.m.

EST.

Those earlier pilot VMs and disks are confirmed deleted.

A separate approved
Episodes9/12 pilot is waiting for L4 capacity.

Its first round found stockouts
in all five requested zones; the provisional VM was rolled back before startup.

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

All **30 historical recipes are inventoried**.

Portable code now covers the
36 tracking-repair compute nodes for 21 episodes and the fresh base path for
**28 episodes**.

Historical sources for13/27 were recovered from their producing
Git commit.

Special original runs3/16 and the later-profile correction branches
remain to be ported.

Implemented coverage for T1-10/T1-11 is therefore19episodes;
unsupported selections fail before inference.

**31 CPU tests and 13 native offline entry-point checks pass.** The latter check
imports/CLI startup without GPU inference.

An import-shadowing issue found during
these checks was corrected by executing each native stage in its frozen source
directory. [Adapter evidence](FRESH_TRACKING_ADAPTER.json),
[native checks](FRESH_TRACKING_NATIVE_CHECKS.json),
[private implementation commit](https://github.com/isyed/v2d-reconstruction/commit/09f4da746c4190b44bb48e353df3dd084b9b4cf9).

The new pilot exercises translation-window recovery (Episode9) and independent
anchor/bounded recovery (Episode12).

The approved118.6MBprivate payload is
uploaded and pinned.

The controller retries every120seconds for up to2.5hours and runs without the
laptop or chat.

Any successfully allocated worker is also independent.

No training or competition upload is performed.

**GPU inference results are not
available yet.** This page records the last checked status; it is not a live cloud
monitor.

The local refresh tool and progress file are documented in the private repo.

**Next:** evaluate this new tracking path, continue the remaining special/later
correction adapters, then complete the raw-video entry point and final
organizer-accessible archive.

The archive below remains a verified foundation,
not a complete raw-video reproduction container.

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
