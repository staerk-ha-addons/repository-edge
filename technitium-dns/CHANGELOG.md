# Changelog since v15.3.0
- 👷 Harden auto-release: SHA-pin checkout v7 & set make_latest (#39)

## Description

Two fixes to the auto-release workflow, plus it resolves the duplicate
`actions/checkout` bump PRs.

### 1. `make_latest=true` on publish
v15.3.0 published correctly but did **not** receive GitHub's "Latest"
badge (the API still returned v14.3.0). Cause: the workflow publishes by
PATCHing the draft with `draft=false`, but flipping a draft to published
via PATCH does not re-run GitHub's latest-release evaluation. Setting
`make_latest=true` explicitly fixes this for future releases.

### 2. `actions/checkout` v6 → v7 (SHA-pinned)
This is the only direct `actions/checkout` usage in the repo. Pinned to
the `v7.0.0` commit SHA to match the repo's existing pin convention and
satisfy zizmor's `unpinned-uses` rule — which is exactly why the
bare-tag bumps in #36 and #37 fail their zizmor check.

v7's breaking change (blocking fork-PR checkout in
`pull_request_target`/`workflow_run`) does not affect this step: it
specifies no `ref` and only runs on `push`-triggered runs, so it checks
out `main`, not untrusted PR code.

## Type of Change

- [x] 👷 CI / maintenance

## Related

- Supersedes #36 and #37 (duplicate checkout bumps) — closing both.

---------

Co-authored-by: Claude Opus 4.8 <noreply@anthropic.com> 
