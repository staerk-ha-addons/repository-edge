# Changelog since v0.1.0
- Refactor configuration files and improve formatting for Technitium DNS Server; enhance readability and maintainability. 
- Refactor scripts and improve YAML translations for Technitium DNS Server; enhance readability and maintainability. 
- Prettified Code! 
- Enhance Technitium DNS Server with new features and improvements

- Updated AppArmor profiles to include new scripts for API utilities, initialization, and certificate watching.
- Modified configuration file to support additional DNS forwarding options and logging capabilities.
- Improved certificate management script to handle self-signed certificates and PKCS12 generation more robustly.
- Added new API utilities for better interaction with the Technitium DNS Server.
- Implemented a certificate watch script with debouncing to reduce unnecessary updates.
- Created initialization script for the DNS server to validate configuration and set up necessary parameters.
- Added translations for new configuration options in English.
- Introduced new service dependencies and run scripts for better service management. 
- Refactor AppArmor profile and configuration for Technitium DNS Server; remove unused signal handling and adjust port settings for improved functionality. 
- Remove unused cert-convert-startup dependency script 
- Enhance PKCS12 certificate generation logging and instructions for Technitium DNS Server configuration 
- Remove deprecated custom regex configurations from Renovate JSON 
- Add Renovate configuration for automated dependency management 
- Update README and documentation for Technitium DNS Server add-on installation and support details 
- Add release drafter configuration for automated changelog generation 
- Add GitHub workflows for Lock, Release Drafter, and Stale with scheduled triggers 
- Update workflow references to use hassio-addons for consistency and improve logging message in certificate watch script 
- Prettified Code! 
- Add VS Code tasks configuration for Home Assistant and addon management 
- Update .gitignore: exclude VS Code tasks.json from being ignored 
- Refactor certificate management: remove deprecated cert-convert startup and watch scripts, and add new certificate watch functionality. 
- Prettified Code! 
- Refactor Technitium DNS add-on: enhance certificate management, update AppArmor profile, and improve Dockerfile permissions 
- Refactor AppArmor profile: enhance capabilities and permissions for S6 overlay scripts, DNS service, and certificate utilities. 
- Refactor AppArmor profile: remove complain flag and enhance permissions for S6 overlay scripts and specific utilities. 
- Enhance AppArmor profile: clarify S6 overlay scripts and services permissions. Update certificate utility logging for better clarity on self-signed certificate generation. 
- Refactor SSL certificate generation scripts: restore and enhance the startup process for PKCS #12 certificate generation, ensuring proper logging and error handling. 
- Refactor SSL certificate handling: improve configuration checks, ensure directory existence, and enhance logging for certificate generation and expiration warnings. 
- Prettified Code! 
- Enhance documentation and logging for SSL certificate management

- Updated DOCS.md to improve clarity on default credentials, configuration steps, and port settings.
- Added structured notes for SSL certificate setup and DNS-over-HTTPS configuration.
- Improved log messages in certificate conversion scripts for better visibility during startup and monitoring. 
- Refactor DOCS.md to remove outdated sections and improve structure 
- Remove CHANGELOG.md as it is no longer needed for the Technitium DNS Server add-on. 
- Add README for Technitium DNS Server add-on with features, installation instructions, and support information 
- Merge pull request #1 from staerk-ha-addons/cert

Enhance Technitium DNS Server add-on documentation and configuration 
- Update CI and Deploy workflows to ensure proper branch handling and secret management 
- Enhance certificate generation and monitoring scripts for Technitium DNS Server 
- Refactor DNS server startup script and enhance certificate generation process 
- Merge branch 'main' into cert 
- Prettified Code! 
- Enhance Technitium DNS Server add-on documentation and configuration

- Updated README.md and DOCS.md with detailed features, installation, and configuration instructions.
- Improved Dockerfile by adding necessary packages for SSL certificate management.
- Enhanced config.yaml to include SSL certificate generation options.
- Added scripts for automatic PKCS #12 certificate generation and monitoring.
- Fixed service naming in finish script and ensured proper error handling in run script. 
- Prettified Code! 
- Init 
