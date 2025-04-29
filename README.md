# Staerk Home Assistant Add-ons

[![License][license-shield]][license]

## WARNING! THIS IS AN EDGE VERSION!

> [!CAUTION]
> This Home Assistant Add-ons repository contains edge builds of add-ons.
> Edge builds add-ons are based upon the latest development version.

- They may not work at all.
- They might stop working at any time.
- They could have a negative impact on your system.

This repository was created for:

- Anybody willing to test.
- Anybody interested in trying out upcoming add-ons or add-on features.
- Developers.

If you are more interested in stable releases of our add-ons:

<https://github.com/staerk-ha-addons/repository>


## About

Home Assistant add-ons repository by Jeppe Stærk. These add-ons extend the functionality of your Home Assistant installation.

## Installation

Click the button below to add this repository to your Home Assistant instance:

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https://github.com/staerk-ha-addons/repository-edge)

Or use the following URL to add this repository:

```txt
https://github.com/staerk-ha-addons/repository-edge
```

## Add-ons

### &#10003; [Technitium DNS Server][addon-technitium-dns]

![Latest Version][technitium-dns-version-shield]
![Supports armhf Architecture][technitium-dns-armhf-shield]
![Supports armv7 Architecture][technitium-dns-armv7-shield]
![Supports aarch64 Architecture][technitium-dns-aarch64-shield]
![Supports amd64 Architecture][technitium-dns-amd64-shield]
![Supports i386 Architecture][technitium-dns-i386-shield]

Self-hosted DNS server with Home Assistant add-on integration.

[:books: Technitium DNS Server add-on documentation][addon-doc-technitium-dns]


## Support

Got questions?

- Create an issue on GitHub for bug reports, feature requests, or questions
- Add a ⭐️ [star on GitHub](https://github.com/staerk-ha-addons/repository-edge) to support the project

## Acknowledgments

Special thanks to [Franck Nijhof][frenck] and the [Home Assistant Community Add-ons][ha-addons] project for their invaluable work. This add-on heavily relies on their foundation:

- Base container images
- CI, workflows and best practices
- Readme and docs templates

Their open-source contributions make add-ons like this possible.

## License

MIT License - Copyright (c) 2025 Jeppe Stærk

[addon-technitium-dns]: https://github.com/staerk-ha-addons/addon-technitium-dns/tree/0f8c162
[addon-doc-technitium-dns]: https://github.com/staerk-ha-addons/addon-technitium-dns/blob/0f8c162/README.md
[technitium-dns-issue]: https://github.com/staerk-ha-addons/addon-technitium-dns/issues
[technitium-dns-version-shield]: https://img.shields.io/badge/version-0f8c162-blue.svg
[technitium-dns-aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[technitium-dns-amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[technitium-dns-armhf-shield]: https://img.shields.io/badge/armhf-no-red.svg
[technitium-dns-armv7-shield]: https://img.shields.io/badge/armv7-no-red.svg
[technitium-dns-i386-shield]: https://img.shields.io/badge/i386-no-red.svg
[frenck]: https://github.com/frenck
[ha-addons]: https://addons.community/
[license]: https://github.com/staerk-ha-addons/repository/blob/main/LICENSE
[license-shield]: https://img.shields.io/github/license/staerk-ha-addons/repository.svg