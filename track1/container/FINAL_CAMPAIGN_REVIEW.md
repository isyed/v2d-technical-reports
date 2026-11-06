# Built archive and Episode 8 review

The final **49,107,013,120-byte OCI container archive is built and backed up**.
It passed all **24 official stored-output checks** and **14 native import checks**.
The Episode 8 worker independently downloaded and verified the archive before
executing its fresh-video commands. Archive identity is retained in
`FINAL_OVERLAY_BUILD_RECEIPT.json` in the local campaign directory.

Episode 8's T1-10 command completed. T1-11 stopped at the original iron fallback
guard: both primary fits failed the `grasp_worst_gap` and `release_separation`
checks. The historical fallback only addresses localized silhouette failure,
so applying it here would be unjustified. Acceptance limits were not relaxed,
and historical predictions were not substituted.

Completing a command does not certify reproduction. Over Episode 8's 454 scored
frames, the fresh T1-10 object translation differs from the saved result by a
mean **4.52 cm**, and object rotation by a mean **92.58 degrees**. The mesh bytes
match. These are fresh-versus-saved pose differences, **not Kaggle scores**.
The large rotation difference needs an upstream recipe/registration audit; the
current evidence does not establish whether it is ambiguity or an adapter error.

Episode 5 never started. Google reported a **one-GPU global quota** while Episode
8 occupied that slot. The controller incorrectly retried the second allocation
and then failed when its acquisition deadline expired during a pending operation.
The controller code now serializes GPU allocations and retains pending operations
without abandoning monitoring. Regression tests pass: **54 total tests**. This
fix is prepared for future use; no replacement controller or GPU has been launched.

Episode 8's 82,572,899-byte evidence archive was downloaded with its pinned
generation, and its MD5 was independently verified. Logs, reports and compact
fresh exports are extracted locally. The backed-up Episode 8 VM was deleted
immediately on review, and a live VM query confirms **zero campaign VMs**.

The official container skill requires the exact stored outputs and offline
pipeline, but recommends fresh Track 1 reproduction on **two or three sequences**,
not all 30. Earlier pilots already exercised Episodes 11, 29, 9 and 12; Episode 8
was extra branch coverage. Those runs include unresolved numerical differences,
so the handoff must still distinguish artifact verification from fresh reproduction.

**Recommendation:** defer optional Episode 5 testing, investigate the confirmed
Episode 8 issue using existing evidence first, and arrange organizer access to
the preserved archive with an accurate limitations report. Further GPU validation
should target a demonstrated fix. One of the two approved L4 allocations remains
unused.

## Subsequent source audit and delivery

The source audit localizes Episode 8's material mismatch before the late corrections, but does not establish a numerical fix. The archive's limited-duration read-only download link has been tested anonymously; the temporary signing grant was removed. See [the audit](EPISODE8_REPRODUCTION_AUDIT.md) for supported findings, causal limits and exact archive identity. The signed bearer URL is kept out of Git.
