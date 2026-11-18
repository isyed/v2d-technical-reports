# Track 1 container handoff

Updated November 17, 2026. This is the same container page entered in the original
technical-report form. The report PDF and the counted submissions are unchanged.

## Rebuilt archive

The container was recreated locally using the existing verified artifact image,
original reconstruction adapter and runtime images, and hash-verified model
files. All **24 official stored-output checks pass**, along with **14 native
adapter imports**, **two offline model-runtime imports**, and the CPU recipe/input
check for Episodes 7 and 20. Both offline fresh-video runs now complete, but
their object poses differ materially from the stored reconstructions.

- Image: `longbot-v2d-track1:rebuilt-20261117`
- OCI manifest digest: `sha256:bee40bbe3fc80407132f4031e86b3207268ac8f051297ce62ecde2e46a274113`
- OCI configuration digest: `sha256:9eb8412d29788cf359792d21da76002716def5f3942addfdfd91f8012542129a`
- Archive: `longbot-track1-four-profile.oci.tar`
- Archive bytes: **50,276,077,568**
- Archive SHA-256: `f3fc4d1b704435b9d26bb8f86d75341cac954194a8859cf3a5af310006028ae5`

These checksums identify the rebuilt archive. GitHub verified the size and
SHA-256 of all 26 archive parts. Sign in as `Nvidia-V2D-Challenge` and download
the numbered parts, `DELIVERY_MANIFEST.json`, and `restore_archive.py` from
the [private Track 1 release](https://github.com/isyed/v2d-reconstruction/releases/tag/track1-container-rebuild-20261117).
The organizer account already has access to the implementation repository. Run
`python3 restore_archive.py --load` from the download directory to verify the
parts and load the image. `RESTORE.md` in the release lists the download command
and offline verification steps.

See [checksums](CHECKSUMS.sha256), [rebuild status](REBUILD_STATUS.json), and
[official verification reports](verification_20261117).

## Submission coverage

The image preserves clean producing Git checkouts, the exact submitted files,
and all 30 saved reconstructions and meshes for each profile:

| Profile | Producing commit | Coverage |
| --- | --- | --- |
| T1-02 | `9337b8d1550a69aeaca9c498f5e8a3ce8ab0544a` | CD-H tie, ACC-O, PEN |
| T1-03 | `4054ffdf78b1ab0658c8e949d216089bd9a138d6` | CD-H tie |
| T1-10 | `1529ad1af98aa4409e8a8d859cc2ee6654f9eca9` | ACC-H |
| T1-11 | `8eb8b6346f3150edfb84b20c1d039b148697ce7a` | CD-O; designated in the report form |

No original file's provenance was rewritten. The kit verifier is unchanged.
T1-11 retains the form's IDs 57605527, 57605528, 57605530, 57605533 and 57605538.
Metric-wise best files from the other profiles are included independently.

## Fresh-video comparisons

These numbers compare all frames of the fresh outputs against the saved T1-11
exports. They are reproduction differences, not hidden-label competition scores.

| Episode | Frames | Mean object translation difference | Mean object rotation difference | Maximum translation difference |
| --- | ---: | ---: | ---: | ---: |
| 7 | 777 | 8.18 cm | 73.48° | 118.30 cm |
| 20 | 549 | 2.92 cm | 30.28° | 15.65 cm |

The mesh bytes and object scales match exactly in both samples. The pose
differences are substantial, and reproduction of the submitted scores remains
unverified. Award eligibility remains subject to organizer validation.
Detailed evidence is available for
[Episode 7](verification_20261117/episode7_fresh_comparison.json) and
[Episode 20](verification_20261117/episode20_fresh_comparison.json).

## Run and validation scope

Load the OCI archive using `docker load -i longbot-track1-four-profile.oci.tar`.
Run `/submission/run.sh verify` inside the image without network access.
Fresh reconstruction accepts `reproduce --label t1_11 --episodes 7 20
--dataset-root /data --output /output/fresh`; mount released data read-only and a
separate writable output directory. A CUDA-compatible NVIDIA GPU is required for
inference. Original runtime images and all 720 required model files are included.

Stored-output verification does not certify fresh-video numerical reproduction.
The historical Episode 8 mismatch remains unresolved and is explicitly disclosed
in [the audit](EPISODE8_REPRODUCTION_AUDIT.md). No complete all-30 fresh-score
reproduction claim is made. Frozen RGB-derived mesh priors and source annotations
are reused; mesh generation is not repeated during fresh reproduction.

The organizers' account `Nvidia-V2D-Challenge` currently has access to the private
[implementation repository](https://github.com/isyed/v2d-reconstruction).
Historical receipts are retained for transparency, including the
[previous handoff text](HISTORICAL_HANDOFF_20261106.md). Their old download link
has expired and is not the rebuilt archive's delivery link.
