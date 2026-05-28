# GitHub Copilot Instructions for Riven AI

This file gives GitHub Copilot per-repository guidance. It is a thin overlay on top of [`AGENTS.md`](../AGENTS.md), which is the source of truth for ALL AI agents at Riven AI. If guidance here conflicts with AGENTS.md, AGENTS.md wins.

## Read First

Before suggesting code, Copilot MUST be aware of:

1. [`AGENTS.md`](../AGENTS.md) — scope of authority, what agents may and must not do.
2. [`CONTRIBUTING.md`](../CONTRIBUTING.md) — branching, commits, PR workflow.
3. [`SECURITY.md`](../SECURITY.md) — vulnerability disclosure rules.
4. The repository-local `README.md`.

## Suggestion Style

- Prefer the repository existing patterns over inventing new ones. Match the surrounding code's idioms.
- Default to the standard library. Justify new dependencies in the PR body.
- Write small, focused functions. Avoid clever one-liners that hide intent.
- Add type hints in Python and TypeScript. No untyped exports.
- Use Conventional Commits in suggested commit messages: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `test:`, `perf:`, `build:`, `ci:`, `revert:`.

## Tests

- Any new function or class gets a unit test in the same PR.
- Prefer table-driven / parametrized tests for branching logic.
- Never silence or skip a failing test to make CI green.

## Things to NEVER Suggest

- Hardcoded secrets, API keys, tokens, passwords, or `.env` contents — even in tests or examples.
- Code that reads or transmits files under `secrets/`, `data/`, `prod/`, or `.env*`.
- Disabling CodeQL, secret scanning, Dependabot, or branch protection.
- `--force` git pushes to protected branches.
- Bypassing the PR review process for `main` or release branches.
- Auto-merging PRs that change CI/CD workflows touching deploy, release, or secrets.

## Things That Require Human Confirmation

Copilot Workspace, Copilot Chat, and Copilot Coding Agent MUST surface a confirmation prompt before:

- Opening a PR against `main` directly (use a feature branch).
- Modifying any file under `.github/workflows/`.
- Adding or rotating environment variables, secrets, or tokens.
- Adding a new external service dependency, SDK, or network call.
- Changing licensing, copyright headers, or `LICENSE`.
- Renaming, archiving, or deleting files in bulk.

## When Acting Through Copilot Coding Agent

- Every PR MUST be labeled `agent:copilot`.
- Every commit MUST include the trailer `Co-Authored-By: Copilot <copilot@riven.ai>`.
- Every PR body MUST follow the structure in `.github/PULL_REQUEST_TEMPLATE.md` (What / Why / How / Risk / Verification / Rollback).

## Repository-Specific Overrides

Individual rivenai/* repos MAY add their own `.github/copilot-instructions.md` to layer repo-specific guidance on top of this org-wide file. Repo-local instructions take precedence within that repo.
