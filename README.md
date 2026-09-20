# Mealie

> TOS 7 application package for **Mealie** — platform integration only.
> The application itself is provided by the upstream project, unmodified.

## Overview

Self-hosted recipe manager with meal planning, shopping lists and household sharing.

上游项目 / Upstream: <https://github.com/mealie-recipes/mealie>
上游许可证 / License: **AGPL-3.0**

## Features

- Recipe collection with automatic parsing and import
- Weekly meal planner and shopping lists
- Household sharing with multiple users
- REST API and mobile-friendly web UI

## Installation

1. Requirements: TOS 7.0+ and Docker Engine (install from the TOS App Center)
2. Install from the TOS App Center
3. Open the app and complete initial configuration

## Usage

1. Access URL: `http://${ip}:18802`
2. Default credentials: see upstream documentation
3. Key settings: see upstream documentation

## Permissions

| Permission | Rationale |
|---|---|
| Network: port 18802 | Web UI access |
| File system: `/Volume*/DockerAppData/shh2-mealie/` | Application data persistence |
| User: shh2mealie | Isolated non-root service execution |

## Configuration

See `config.ini` for platform metadata; see `docker-compose.yml` for runtime configuration.

## Ports

| Port | Protocol | Purpose |
|---|---|---|
| 18802 | TCP | Web UI (Mealie) |

## Support

- Documentation: https://github.com/mealie-recipes/mealie
- Issue tracker: https://github.com/mealie-recipes/mealie/issues
- Community: https://github.com/mealie-recipes/mealie

## Security & Compliance

- **License**: AGPL-3.0 — full text in [`LICENSE`](./LICENSE)
- **Attribution**: see [`NOTICE`](./NOTICE)
- **Privacy Policy**: see [`PRIVACY.md`](./PRIVACY.md)
- **Vulnerability scan**: `trivy-report.txt` attached to each Release (HIGH/CRITICAL must be 0)
- Runs as a non-root dedicated user; no privileged mode, no host network

## Changelog

### v1.0.2 (2026-09-20)
- Compliance update: added LICENSE / NOTICE / PRIVACY materials,
  declared upstream license inside the package, added container healthcheck

### v1.0.0
- Initial release

## License

**AGPL-3.0** — this packaging repository is distributed under the same license as the
upstream project. Full text: [`LICENSE`](./LICENSE).
