# Four-profile raw-video adapter: implementation and validation status

All 30 episode paths and all four counted profiles now have executable adapter
code.

**This is implementation coverage, not verified fresh GPU reproduction of
all 120 profile/episode combinations.** The final overlay has not yet been built
or uploaded.

The independently verified 49.0GB foundation remains preserved.

The eleven formerly missing late-profile cases are Episodes0, 1, 2, 3, 4, 5, 8, 15, 16, 17
and 22.

The adapters preserve the historical dependencies:

| Stage | Episodes | Preserved behavior |
|---|---|---|
| Selected refinement | 5, 17, 22 | Fresh initializer from controlled baseline; export after 29 updates of the original 50-update / 75-step schedule / 5-step warmup configuration, before penetration activates |
| Fixed-depth initialization | 0, 1, 2, 3, 16 | 80 updates, 5 cm XY bound; depth and human parameters preserved |
| Hoop geometry/pose | 0–2 | Retain main connected ring; use fixed-depth fit, not rejected depth proposal |
| Orientation | 3, 4, 5, 16, 17 | 40 updates; only object rotation selected |
| Block orientation |15|Original visibility intervals and 40 updates; rotation only |
| HumanB, T1-10 only |8| Fresh ViTPose observations, 40 updates, fixed root/identity/object, smoothed correction with exact frame 90 anchor |
| Iron, T1-11 only |8|Branches from T1-09 without HumanB; fixed/shared-scale screening, reviewed transition fallback, guarded motion repair |

The source bundle includes seven immutable native-library snapshots and1,044
hashed files (201,728,417 bytes).

It contains source code, RGB-derived mesh priors,
source prompts, 27 RGB-derived person-mask patches and topology hand indices.

The hand indices were extracted alone: historical paired human geometry and
predicted trajectories were deliberately excluded.

No saved final trajectories,
checkpoints, credentials or neural-network weights are in this adapter bundle.

Source relocation changes only explicitly mapped absolute path string literals.

Each derived source records original/derived hashes and all literal changes.

Numerical constants and conditions remain unchanged.

Producing checkouts,
counted files, original commit URLs and the official verifier are untouched.

Branch-specific output assembly rejects changes to unrelated fields.

If fresh
iron screening chooses a different branch, execution stops with evidence; it
does not silently substitute the historical prediction or relax acceptance.

The public container command is implemented as:

```sh
docker run --rm --gpus all --network none --shm-size=8g \
  -v /absolute/released-dataset:/data:ro \
  -v /absolute/new-output:/output \
  IMAGE reproduce --label t1_11 --episodes 5 8 \
  --dataset-root /data --output /output/run1
```

`--plan-only` performs input-identity and plan checks without inference.

Separate
output roots preserve past evidence.

Episodes may be space- or comma-separated.

Outputs include stage logs, source derivation receipts, compact evidence and a
reproduction receipt.

Mesh generation is **not** repeated: the original frozen
RGB-derived mesh priors are reused and explicitly disclosed.

Episode 3 retains the original nominal 300 / actual 301 update optimizer behavior.

Its historical refinement alone took approximately 7 hours.

Execution rejects the
default 45-minute stage timeout for this case; an explicit timeout of at least
30,000 seconds and an adequate separate worker lifetime are required.

A standard
three-hour worker must not be advertised as sufficient for that path.

Validation completed locally:

- 46 CPU tests pass, including 120 individual profile/episode plan checks, complete
  all-30 plans, branch lineage, immutable source derivation, field preservation,
  nonfinite/shape rejection and fresh-command dispatch.
- 14 new imports pass inside the exact original CPU runtime, with networking and
  GPUs disabled.

Five top-level historical compute scripts compile; importing
  them would execute inference, so their execution remains a GPU validation.
- The official Python 3.14 mesh-budget helper successfully materializes the review
  geometry with the isolated packer's dependency versions.
- The earlier 35 tests / 24 native base checks and two completed GPU pilots remain
  recorded independently.

Those pilots executed fresh sequences 11, 29, 9 and 12.

**Remaining acceptance work:** build and independently validate the overlay
archive; exercise representative late branches on GPU; preserve and explain the
material Episode 12/29 numerical differences; provide organizer download access
under the applicable asset licenses.

An archived foundation, CPU checks, or an
implemented adapter alone does not establish a complete competition handoff.

The new cloud review is prepared by `prepare_final_overlay.py`; it does not
upload, launch or spend.

Any actual launch requires an
explicit numeric approval and pinned upload generation.

Existing thermal limits,
independent control, backup and automatic deletion remain required.
