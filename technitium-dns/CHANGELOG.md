# Changelog since v15.3.0
- 👷 Make Renovate reliably auto-upgrade the repo (#40)

## Description

Renovate already had auto-merge fully enabled (`automerge`,
`platformAutomerge`, squash, no dashboard approval), but two things
blocked it in practice. This removes both.

### 1. Remove `.github/dependabot.yaml`
Dependabot was configured for `github-actions`, `docker`, and
`devcontainers` — all of which Renovate already handles. Dependabot's
PRs **don't** auto-merge, so it just produced competing/duplicate PRs
(e.g. the `actions/checkout` v6→v7 double-up in #36/#37). Renovate owns
everything now.

### 2. Add `helpers:pinGitHubActionDigests`
The repo's zizmor check enforces `unpinned-uses` (Actions must be
SHA-pinned). Renovate was proposing **bare tags** (`@v7`), which can
never pass zizmor → those PRs could never go green → never auto-merged.
Pinning to commit SHAs makes Action bumps pass zizmor **and** keeps them
updated (Renovate tracks the digest, with a version comment). Also a
supply-chain win.

## Effect
- One bot (Renovate), no duplicates.
- DNS server / base image / .NET / Debian package / Action /
devcontainer updates all create + auto-merge once CI is green.
- CI still gates every merge (Renovate won't merge a red PR — exactly
what stopped the broken .NET 10 bump from landing).

## Type of Change
- [x] 👷 CI / maintenance

## Follow-up (not in this PR)
- Renovate deprecation: `fileMatch` → `managerFilePatterns` in the
custom managers. Non-blocking; left out here to avoid touching the
update-detection regexes in the same PR that enables auto-merge.

Co-authored-by: Claude Opus 4.8 <noreply@anthropic.com> 
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
