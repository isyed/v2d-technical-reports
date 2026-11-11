# Review policy

Every change to `main` requires a pull request and approval from `@isyed`, the sole
code owner of all paths, including `.github/CODEOWNERS`. New commits dismiss stale
approvals, conversations must be resolved, and administrators cannot bypass the
rule. Force pushes and deletion of `main` are disabled. The intended API payload
is `.github/main-protection.json`; GitHub settings enforce it. No CI requirement is
invented for this repository, which currently has no automated test workflow.

GitHub does not let a PR author approve their own PR. An automated contributor
therefore needs a separately authorized account or GitHub App so the owner can
review its work. Do not approve on the owner's behalf or weaken protection to
merge. Preserve blocked work on its feature branch and report the missing review.
The owner retains the ability to edit repository settings.

Delete a feature branch only after its commits are reachable from `main`. Keep
credentials, private captures, checkpoints and unpublished experiment data out of
this public repository. The ownership-policy change does not authorize publishing
new experiment material here.
