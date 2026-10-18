# Omnipha

**Full Linux on phones.** Omnipha turns used phones into general-purpose Linux computers: agent hosts (Claude Code, Codex, OpenClaw, Hermes), home servers, 3D-printer drivers, NAS nodes, camera and sensor platforms. A used 100-Euro phone with 4-8 GB RAM, 128 GB storage, display, battery, cameras and sensors replaces a 400-Euro SBC build.

Built on mainline Linux and Nura (postmarketOS) packaging, but centralized, CI-first, and agent-friendly.

## Repository map

| Repository | Purpose |
|---|---|
| [`ports`](https://github.com/omnipha/ports) | Device packages, firmware packaging, patches, machine-readable device database |
| [`builder`](https://github.com/omnipha/builder) | Build tool (pmbootstrap fork): server profiles, SSH key injection, headless CI mode |
| [`images`](https://github.com/omnipha/images) | Flashable image definitions and release builds per device |
| [`linux-<soc>`](https://github.com/omnipha?tab=repositories) | Kernel mirrors: `upstream` branch (bot-synced) + `omnipha` branch (our patches) |
| [`pmaports-mirror`](https://github.com/omnipha/pmaports-mirror) | Read-only bot mirror of upstream pmaports |

## How to contribute

Humans and AI agents are both welcome. See [CONTRIBUTING.md](CONTRIBUTING.md). Every repository contains an `AGENTS.md` with machine-readable orientation. Every device PR is built by CI into a flashable image automatically.

## Kernel policy

- Active upstream kernel trees are **referenced**, not forked.
- Inactive or abandoned trees are **mirrored** here (`linux-<soc>` repos, bot-synced) so work never blocks on an external maintainer.
- Each kernel repo documents upstream source, sync status, and activity score in `UPSTREAM.md`.

## License

Individual repositories keep their upstream licenses (GPL for pmbootstrap/pmaports derivatives). New Omnipha tooling is MIT unless stated otherwise.
