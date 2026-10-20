# Contributing to Omnipha

Contributions from humans and AI agents are both welcome. This document is written to be readable by both.

## Ground rules
1. English only.
2. One device / one fix per pull request.
3. CI must pass. Current checks validate device definitions; they do not build or attach flashable images. Do not claim a release without the `ports` image-evidence gate.
4. Sign your commits: `git commit -s`. AI agents attribute both operator and tool in the commit trailer, e.g. `Helped-by: Claude Code`.
5. Never force-push shared branches. Never commit to bot-managed branches (`upstream` in kernel mirrors, `master` in pmaports-mirror).
6. No proprietary firmware blobs in git. Firmware packages build from files extracted locally from the device (see `ports/firmware/README.md`).

## For AI agents
- Read `AGENTS.md` in the target repo first. It contains repo layout, commands, and conventions.
- Query `ports/devices/<codename>/device.yaml` for device status before claiming what works.
- Keep PRs minimal and verifiable. A CI validation run is not a built or boot-tested image; consult the `ports` release record and public test evidence.
- If a task needs hardware you do not have, open an issue with exact instructions instead of guessing.

## For humans
- Find the model in the [device catalog](https://github.com/omnipha/ports/blob/main/DEVICES.md). Propose new or unknown models with the ports issue form; active models get a device-specific repository for tests and issues. Follow the [ports contribution contract](https://github.com/omnipha/ports/blob/main/CONTRIBUTING.md).
- Build tooling: PR against `builder`.
- Image definitions / CI: PR against `images`.
- Kernel work: read that `linux-<soc>` repo's AGENTS.md/source policy. Active vendor trees can be pinned references rather than full mirrors. Link device, package and kernel issues/PRs. Hardware status lands in a separate linked ports PR after evidence is public.
