# Changelog since v2026.7.0
- 👷 Switch auto-release to CalVer (decoupled from Technitium version) (#44)

## Description

We moved the add-on to a **CalVer** version (`2026.7.0`) so add-on-only
fixes can ship (the store's `repository-updater` requires strict 3-part
semver, and HA needs each version to sort *higher* than the last). This
updates the automation to match.

**Why it's needed now:** `auto-release.yaml` set the release version to
`DNS_SERVER_VERSION` (e.g. `15.4.0`). But `15.4.0` sorts **below**
`2026.7.0` (semver: 15 < 2026), so the next Technitium bump — which now
auto-merges via Renovate — would have cut a release Home Assistant
treats as *older* than what users already have. It would never ship, and
could confuse the store.

## Changes
- **CalVer**: version is computed as `YYYY.M.PATCH` (patch increments
within a month via the tags API, resets on a new month).
`DNS_SERVER_VERSION` stays purely the upstream Technitium pin that
Renovate manages.
- **Broader trigger**: releases now fire on any change under
`technitium-dns/` (Technitium bumps *and* add-on-only fixes like the
ingress fix), instead of grepping the commit message for
`DNS_SERVER_VERSION`. Add-on fixes now release automatically — no more
manual releases.
- **Safety**: GitHub contexts passed via `env:` (no template injection);
dropped the now-unneeded `actions/checkout` step.
- Keeps the `DISPATCH_TOKEN` publish + `make_latest=true` so the stable
deploy triggers and the release gets the Latest badge.

## Validation
- ✅ yamllint (repo config) clean
- ✅ prettier (repo config) clean
- Verified `2026.7.0 > 15.3.0` and valid semver earlier via
AwesomeVersion + semver.

## Type of Change
- [x] 👷 CI / maintenance

## Note
The Technitium version remains visible in the Technitium web console and
in the release notes (the DNS_SERVER_VERSION bump PRs). The HA add-on
version is now date-based.

Co-authored-by: Claude Opus 4.8 <noreply@anthropic.com> 
