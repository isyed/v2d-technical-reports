# Episode 8: fresh-reproduction mismatch audit

**Status: localized, but not numerically resolved.** The preserved container passes all 24 official stored-output checks. That does not establish that a fresh Episode 8 run reproduces the counted results.

## What the saved evidence establishes

The original input mesh matches the frozen prior byte for byte; the historical and fresh aligned meshes also match. Both fresh runs have identical packed segmentation masks and identical raw MoGe depth hashes. Their SAM3D body predictions differ only at floating-point scale (the largest difference across the saved native parameter arrays is about 3.8e-6). Historical versus fresh masks are close, but not identical: mean object-mask IoU is 0.99385 and human-mask IoU is 0.99545.

Large object rotation divergence is already present in the pre-late-correction exports. The first difference above 10 degrees is frame 203 in the T1-10 run and frame 218 in the T1-11 run. The two fresh base runs themselves differ by a mean 2.73 degrees and a maximum 31.78 degrees. These measurements identify an upstream sensitivity; they do not isolate which earlier operation first caused it.

The bounded tracking source is a sequential local optimizer. Its objective combines silhouette overlap, weak depth agreement and rotation continuity. It has no RGB appearance term. At frame 300, rotations differ by 115.98 degrees while the historical/fresh source-mask IoUs are 0.78495/0.78608. At frame 400, rotations differ by 179.07 degrees and IoUs are 0.61872/0.70361. Thus a good silhouette score cannot resolve this 3D orientation ambiguity. These CPU rasterization measurements use a mesh simplified to 10,000 faces and are diagnostic proxies, not official scores or proof of 3D correctness.

## Why the last branch stops

Across the 454 scored frames, fresh T1-10 differs from its historical output by a mean 4.52 cm in translation and 92.58 degrees in rotation. T1-11 does not export a final reconstruction: its fixed and shared-scale fits fail the unchanged `grasp_worst_gap` and `release_separation` checks. The local fallback was designed only for a localized silhouette failure, so it correctly refuses this different failure class.

At final release frame 543, the fresh baseline already has approximately 0.0015 cm of hand/object separation, whereas the historical baseline had approximately 10.13 cm. This explains why weakening the repair guard would conceal an upstream problem. The gate is a local research selection heuristic, not an additional official container check.

## What is fixed, and what remains open

The validation backup filter omitted compact FoundationPose/recovery pickle stages while retaining their reports. The prepared tooling now retains those stages and the compact MHR initialization files under the existing size ceilings. All **55 CPU tests pass**. This collector fix is not inside the already built archive and has not been cloud-retested.

The completed worker did not retain its aligned depth cache or intermediate rigid tracking pose files. Therefore the exact first divergent optimizer update, the separate effects of changed observations and GPU numerics, and the complete causal chain cannot be proven from that backup. Silhouette ambiguity and numerical sensitivity are supported explanations, not a verified numerical fix. Re-running unrelated episodes would not resolve this failure.

No counted outputs, original producing checkouts, official verifier or acceptance thresholds were changed. Historical trajectories were not substituted into fresh inference. No replacement GPU run or training was started for this audit. A stable future tracker could use independently observed appearance/orientation anchors and multi-frame optimization, but that changes the method and must not be described as reproducing the historical result.

## Archive delivery

The 49,107,013,120-byte archive is preserved at its pinned object generation. A read-only signed GET link was tested anonymously with a 1,024-byte range request after the explicitly approved temporary signing grant was removed. The link expires **November 6, 2026 at 10:55 p.m. EST**. The bearer URL is delivered privately, not committed to Git. The bucket remains private.

Archive SHA-256: `9485c976b13c46b0529bd5296c43014afa4a3abbb7f3324bfd064ef8d36ffbec`.

Image manifest digest: `sha256:8db82172b032896f516373d8bbb3c89bbe81b098eec5eb8ee09477013df3a7db`.

The earlier worker independently downloaded and hash-verified the full archive. The latest anonymous check verifies link access and byte count, not a second full 49.1 GB download. The handoff must disclose the unresolved fresh-reproduction result; it is not certified as matching fresh leaderboard scores.

See [audit data](EPISODE8_REPRODUCTION_AUDIT.json) and [download-access verification](ORGANIZER_ACCESS_VERIFICATION.json).
