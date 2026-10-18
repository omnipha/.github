# Contributing to Omnipha

Contributions from humans and AI agents are both welcome. This document is written to be readable by both.

## Ground rules
1. English only.
2. One device / one fix per pull request.
3. CI must pass. Device PRs automatically build a flashable image; the artifact is attached to the PR.
4. Sign your commits: `git commit -s`. AI agents attribute both operator and tool in the commit trailer, e.g. `Helped-by: Claude Code`.
5. Never force-push shared branches. Never commit to bot-managed branches (`upstream` in kernel mirrors, `master` in pmaports-mirror).
6. No proprietary firmware blobs in git. Firmware packages build from files extracted locally from the device (see `ports/firmware/README.md`).

## For AI agents
- Read `AGENTS.md` in the target repo first. It contains repo layout, commands, and conventions.
- Query `ports/devices/<codename>/device.yaml` for device status before claiming what works.
- Keep PRs minimal and verifiable. Prefer a CI-built artifact as proof.
- If a task needs hardware you do not have, open an issue with exact instructions instead of guessing.

## For humans
- New device support: PR against `ports` (start from an existing device folder as template).
- Build tooling: PR against `builder`.
- Image definitions / CI: PR against `images`.
- Kernel patches: PR against the `omnipha` branch of the respective `linux-<soc>` repo.
