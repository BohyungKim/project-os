# Notion Update Block

Date: 2026-05-08
Project: GitHub-Codex-ChatGPT Source of Truth Setup
Case: Case 2 - New Project Setup

## Current State Update

Confirmed:
- Git CLI is installed: `git version 2.52.0.windows.1`.
- GitHub Desktop is installed at `C:\Users\JohnKim\AppData\Local\GitHubDesktop\GitHubDesktop.exe`.
- `gh` CLI is not installed.
- No `GITHUB_TOKEN` or `GH_TOKEN` is available in the shell.
- Notion access is available.
- Local git folders found:
  - `C:\Users\JohnKim\Documents\New project`
  - `C:\Users\JohnKim\Documents\New project 2`
  - `C:\Users\JohnKim\Documents\New project 3`
  - `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working`

Changed:
- Created the operating `AGENTS.md`.
- Created a beginner-facing `README.md`.
- Created a reusable project `AGENTS.md` template.
- Created today's checklist status.
- Created project registry.
- Created real-time repo status generation script.
- Created nightly automation prompt.

Still incomplete:
- Private GitHub repos need to be created or confirmed by John.
- Local projects need repo-name mapping.
- Local project branches need to be normalized to `main` after first commit.
- Remotes need to be added.
- ChatGPT GitHub connector access must be tested from ChatGPT.

Uncertain:
- Which local folders correspond to `bom-console`, `epicor-chatbot`, `job-bom-comparator`, `transaction-analysis-system`, and `john-executive-assistant-v1`.
- Which GitHub account or organization should own the private repos.

Current project phase:
- Source-of-truth operations setup / pre-publish intake.

## Next Codex Task

Objective:
- Map each real local project folder to its intended GitHub repo name, then prepare one project for safe private GitHub publishing.

Scope:
- Inspect one selected project folder.
- Confirm `.gitignore` and secret safety.
- Add `AGENTS.md`.
- Run available tests or smoke checks.
- Create first commit on `main`.
- Provide exact GitHub Desktop or Git remote instructions.

Out of scope:
- Large code changes.
- Automatic merge to `main` after future feature work.
- Publishing secrets or `.env` files.

Files to inspect:
- Project root files
- `.gitignore`
- `README.md`
- dependency/config files
- test folder

Files to modify:
- `AGENTS.md`
- docs/status file if needed
- `.gitignore` only if secret safety requires it

Acceptance criteria:
- One project has a clean first commit on `main`.
- `AGENTS.md` exists.
- Secrets are excluded.
- Validation command is recorded.
- GitHub publish step is ready.

Validation command:
- `git status --short --branch`
- Project-specific test or smoke command

Report-back format:
- Project Case
- Current State
- Files Changed
- Validation
- Notion Update
- Next Codex Task
- John Review Required

## John Review Required

Yes.

What John must review:
- Which local folder maps to which intended GitHub repo.
- Which GitHub account or organization should own each private repo.
- Whether any discovered `.env` files contain secrets that must remain local.
- Whether ChatGPT GitHub connector can access the created private repos.

Why review is required:
- Codex cannot safely infer project identity or GitHub ownership.
- Publishing the wrong folder or committing secrets would create avoidable risk.

Risk if skipped:
- Wrong repo names/remotes.
- Unstable `main`.
- Secret leakage.
- ChatGPT and Codex may read different source-of-truth states.
