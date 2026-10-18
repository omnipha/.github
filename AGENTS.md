# AGENTS.md — omnipha/.github

This repository holds org-wide conventions. Other omnipha repos inherit from here.

## What lives here
- `README.md` — org profile (rendered on github.com/omnipha)
- `CONTRIBUTING.md` — contribution rules for humans and AI agents
- `ISSUE_TEMPLATE/` — issue templates (device support request, bug, image request)
- `workflow-templates/` — reusable GitHub Actions (mirror sync, image build)

## Conventions for all omnipha repos
- English only. No marketing prose in code/docs; facts and commands.
- Every repo has `AGENTS.md` at root: repo layout, build/test commands, conventions.
- One device per PR. One fix per PR. CI must pass.
- Sign commits (`git commit -s`). Never force-push shared branches.
- Bot branches (`upstream` in kernel mirrors, `master` in pmaports-mirror) are machine-written: never commit to them manually.
- Kernel mirrors: patches go on the `omnipha` branch, rebased by bot, never merged into `upstream`.

## Machine-readable facts
- Org: omnipha. Owner: sprintberlin (Gregor Sprint).
- Build tool: `builder` (pmbootstrap fork). Device packages: `ports`. Images: `images`.
- Device database: `ports/devices/<codename>/device.yaml` — source of truth for device status.
