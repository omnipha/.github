# Omnipha

**Full Linux on phones.** Omnipha turns used phones into general-purpose Linux computers: agent hosts (Claude Code, Codex, OpenClaw, Hermes), home servers, 3D-printer drivers, NAS nodes, camera and sensor platforms. A used 100-Euro phone with 4-8 GB RAM, 128 GB storage, display, battery, cameras and sensors replaces a 400-Euro SBC build.

Built on mainline Linux and Nura (postmarketOS) packaging, but centralized, CI-first, and agent-friendly.

Intended setups, from agent hosts to Home Assistant nodes, wall displays and printer hosts, are cataloged in [USE_CASES.md](USE_CASES.md). Entries there are ideas until device evidence says otherwise.

## Repository map

| Repository | Purpose |
|---|---|
| [`ports`](https://github.com/omnipha/ports) | [Browse devices](https://github.com/omnipha/ports/blob/main/DEVICES.md): machine-readable status, packages, evidence, contribution entry |
| [`builder`](https://github.com/omnipha/builder) | Build tool (pmbootstrap fork): server profiles, SSH key injection, headless CI mode |
| [`images`](https://github.com/omnipha/images) | Image definitions; build/release workflow remains in progress |
| [`linux-<soc>`](https://github.com/orgs/omnipha/repositories) | Shared SoC kernel tracking or mirror, per-repo source policy |
| [`pmaports-mirror`](https://github.com/omnipha/pmaports-mirror) | Read-only bot mirror of upstream pmaports |

## How to contribute

Humans and AI agents are both welcome. Start with the [device catalog](https://github.com/omnipha/ports/blob/main/DEVICES.md) and [contribution guide](https://github.com/omnipha/ports/blob/main/CONTRIBUTING.md). A listed device or package is **not** an installable Omnipha image. Device issues and measured tests live in a `device-<vendor>-<codename>` repo when a port is active; other models remain searchable in `ports`. Image builds and downloads require a separately verified release gate. No device PR automatically builds a flashable image today.

## Kernel policy

- Active upstream kernel trees are **referenced**, not forked.
- Inactive or abandoned trees are **mirrored** here (`linux-<soc>` repos, bot-synced) so work never blocks on an external maintainer.
- Each kernel repo documents upstream source, sync status, and activity score in `UPSTREAM.md`.

## License

Individual repositories keep their upstream licenses (GPL for pmbootstrap/pmaports derivatives). New Omnipha tooling is MIT unless stated otherwise.
