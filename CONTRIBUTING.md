# Contributing to Riven AI

Riven AI is primarily an internal engineering organization. Most repositories under `rivenai` are private and accept contributions only from authorized team members.

This document covers contributions across all repositories in this organization.

## For Riven AI Engineers

1. Branch from `main`. Use a descriptive branch name: `feat/<area>-<short-desc>`, `fix/<area>-<short-desc>`, or `chore/<short-desc>`.
2. Keep commits small and reviewable. Write conventional commit messages (`feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `test:`).
3. Open a pull request against `main`. Fill in the PR template. Link any relevant issues or runbook entries.
4. CI must pass. Resolve all required checks before requesting review.
5. At least one approving review from a code owner is required to merge. Squash-merge unless the PR is explicitly a multi-commit logical sequence.
6. Follow `SECURITY.md` for anything touching auth, secrets, or customer data.

## For External Contributors

We currently do not accept unsolicited code contributions. If you have:

- **A security report** — follow [SECURITY.md](./SECURITY.md). Do not open a public issue.
- **A bug report on a public repository** — open an issue with a minimal reproduction.
- **A feature request** — open a discussion, not an issue, and explain the use case.
- **A partnership or commercial inquiry** — email hello@riven.ai.

## Code of Conduct

All contributors and participants are expected to follow our [Code of Conduct](./CODE_OF_CONDUCT.md).

## Licensing

Unless a repository specifies otherwise in its own `LICENSE` file, code in this organization is proprietary to Riven AI. Do not redistribute without written permission.
