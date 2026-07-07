# Changelog since v2026.7.1
- 🙈 Untrack .claude/settings.local.json and gitignore .claude/ (#48)

## Description

`.claude/settings.local.json` (Claude Code's **local** permission
settings) was accidentally committed via a `git add -A` in #40 and
shouldn't be in the repo.

- **No secrets leaked** — the file contains only local Bash-permission
allowlists (e.g. `Bash(gh pr view:*)`), no tokens or credentials. (It's
a public repo, so worth confirming — nothing sensitive.)
- Local editor/tool state doesn't belong in version control regardless.

## Fix
- `git rm --cached .claude/settings.local.json` (untrack; local copy
kept).
- Add `.claude/` to `.gitignore` so it can't be re-added.

## Type of Change
- [x] 🧰 Maintenance

Co-authored-by: Claude Opus 4.8 <noreply@anthropic.com> 
- 👷 Set release as latest in a separate call (#47)

## Description

**Finding:** v2026.7.1 published correctly but did **not** get GitHub's
"Latest" badge — it stayed on v2026.7.0. Because the add-on store / HA
update detection keys off the latest release, this would keep users from
being offered updates.

**Cause:** `auto-release.yaml` set `make_latest=true` in the *same*
PATCH that flips `draft=false`. GitHub does **not** reliably apply
`make_latest` in that combined draft→publish call (confirmed: a separate
`gh release edit v2026.7.1 --latest` afterwards worked immediately).

## Fix

Publish first, then set "Latest" in a **separate** `gh release edit
"$TAG" --latest` call — applied to both the draft-publish and
fresh-create paths. The separate edit fires a `release: edited` event
(not `published`), so it doesn't re-trigger the deploy.

## Already done manually
v2026.7.1 is now correctly marked **Latest** (fixed by hand); this PR
prevents recurrence for all future auto-releases.

## Validation
- ✅ yamllint + prettier (repo configs) clean

## Type of Change
- [x] 👷 CI / maintenance

Co-authored-by: Claude Opus 4.8 <noreply@anthropic.com> 
