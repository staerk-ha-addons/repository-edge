# Changelog since v1.14.3
- ✨ Auto-compute addon version from DNS_SERVER_VERSION

Addon version is now derived from DNS_SERVER_VERSION:
- Addon major: 1 (hardcoded)
- Addon minor: DNS major version
- Addon patch: DNS minor version

Example: DNS_SERVER_VERSION=v14.3.0 → v1.14.3

Co-Authored-By: Claude Opus 4.5 <noreply@anthropic.com> 
