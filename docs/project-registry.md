# Project Registry

Date scanned: 2026-05-08

This registry tracks local project folders that may need GitHub source-of-truth setup.

## Confirmed Operating Repo

| Field | Value |
| --- | --- |
| Local path | `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of` |
| Purpose | Operating guide/status hub for GitHub-Codex-ChatGPT source-of-truth setup |
| Git status at start | Not a git repository |
| Current local state | Git initialized on `main`; setup docs committed locally |
| Remote state | No GitHub remote configured yet |
| Required action | Create private GitHub repo, add `origin`, push `main` |

## Discovered Local Git Folders

| Local path | Current branch | Remote | Commit state | Notes |
| --- | --- | --- | --- | --- |
| `C:\Users\JohnKim\Documents\New project` | `master` | None found | No commits yet | Python project with `pyproject.toml`, `src/`, `tests/`, `.env`, `.env.example`. Needs `.env` safety review before first commit. |
| `C:\Users\JohnKim\Documents\New project 2` | `master` | None found | No commits yet | Git folder exists, but no visible project files were found in the first scan. Needs intake before publishing. |
| `C:\Users\JohnKim\Documents\New project 3` | `master` | None found | No commits yet | Contains `README.md` and `docs/SUPPLY_READINESS_CHECKER_SYSTEM_PLAN.md`. Needs project name mapping. |
| `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | `docs/agents-guidelines-sync-mainbase` | `https://github.com/BohyungKim/project-os.git` | Latest commit: `2c940d6 docs(state): record pull request and notion update` | Existing Codex work repo for project operating rules. PR #1 needs John review before merge. |

## Structure Intake Summary

Detailed notes are in `docs/project-structure-intake.md`.

- `C:\Users\JohnKim\Documents\New project`: inferred as Microsoft Planner Workload Analyzer MVP. It has a runnable Python package, CLI entry point, config, tests, and report generation. `python -m pytest` passed with 7 tests.
- `C:\Users\JohnKim\Documents\New project 2`: no visible project files outside `.git`.
- `C:\Users\JohnKim\Documents\New project 3`: inferred as PRG Supply Readiness Checker. It is a docs-first architecture planning repo with no implementation or tests yet.
- `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working`: inferred as the `project-os` operating rules workspace connected to GitHub.

## John Mapping Needed

Map each real project to one GitHub repo name:

| Intended repo name | Local folder path | Status |
| --- | --- | --- |
| `bom-console` | John to confirm | Not mapped |
| `epicor-chatbot` | John to confirm | Not mapped |
| `job-bom-comparator` | John to confirm | Not mapped |
| `transaction-analysis-system` | John to confirm | Not mapped |
| `john-executive-assistant-v1` | John to confirm | Not mapped |

## First Safe Action Per Project

Before publishing any existing folder:

1. Confirm the folder is the intended project.
2. Inspect `.gitignore`.
3. Confirm secrets are not tracked.
4. Add root `AGENTS.md` from `templates/AGENTS.project.md`.
5. Run the project's tests or smoke command.
6. Commit to `main`.
7. Publish as a private GitHub repo.
