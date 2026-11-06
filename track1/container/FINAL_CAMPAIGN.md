# Final Track 1 container build and validation campaign

The user approved the exact 132,632,976-byte payload.
It is uploaded at its reviewed private destination, with generation
`1793961303973325` and SHA-256
`4738ca0f3ee92e52916bd14432949e7f3cded45807e40eb8d4d7fa1c40213ac0`.
Both the builder and controller are running. The local laptop is not required
for build completion, L4 capacity retries, validation, backup or deletion.

The CPU builder verifies and restores the pinned foundation, builds the adapter
overlay, runs all 24 official stored-output checks plus 14 native import checks,
then exports and uploads a new OCI archive with its manifest/config digests and
SHA-256. The archive must pass those checks and its backup must finish before the
controller creates any L4 worker.

There are at most two L4 allocations: Episode 5 exercises the short selected
human/object refinement and orientation branch; Episode 8 exercises T1-10's
HumanB branch and T1-11's iron sequence/motion branch. They invoke the shipped
fresh-video entry point and compare stored reconstructions only afterward.
Changed screening decisions are reported as failures or partial validation;
historical predictions are never substituted to manufacture a pass.

The L4 limits remain 60 W, pause at 82°C, resume at 74°C and stop at 83°C. Every
compute worker has a three-hour provider DELETE limit and an auto-delete boot
disk. The small controller has a six-hour fallback limit so it can cover the
build, capacity retries and both workers. It deletes workers once their backup
markers appear, then deletes itself.

Automatic approval review rejected a new builder-scoped instance-admin binding.
**No IAM binding was added.** The deployment instead uses the existing
`v2d-tier3-controller` account's already granted instance create/delete
permissions. The artifact-reading worker account receives no additional rights.
Only small lifecycle metadata is mirrored into the controller's pre-authorized
storage prefix; videos, models, archive and reconstruction evidence remain in
the private Track 1 award-handoff prefix. This resolves the cleanup issue without
the requested permission grant.

Local progress is in
`runs/award_handoff/container/final_overlay1/PROGRESS.txt` and mirrored to
`runs/award_handoff/container/PROGRESS.txt`. The local monitor refreshes once a
minute while the laptop is running. It does not control the cloud jobs. After a
local reboot, refresh explicitly with:

```sh
python3 tools/award_container/refresh_final_status.py \
  --run-dir runs/award_handoff/container/final_overlay1 \
  --gcloud /path/to/gcloud
```

This campaign performs no actor training, Kaggle upload, form resubmission or
Episode 3 long refinement. Final numerical acceptance and an organizer-accessible
archive link remain to be established after cloud results are reviewed. The
technical report PDFs, counted files, producing commits and official verifier
remain unchanged.
