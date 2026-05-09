# Project Registry

Updated: 2026-05-09 10:56 -04:00

Purpose: make `project-os` the central control tower for Codex and ChatGPT continuity. This file tracks where each currently accessible local project lives, what it appears to be, whether it already has its own GitHub source-of-truth repo, and the next safe onboarding action.

## Control Tower Rule

`project-os` is not where all application code should live. It is the central registry and operating layer.

Each real project should eventually have its own GitHub repository with:

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

## Detected Projects

| Project | Local Folder | Classification | Has Code | Has Tests | Git | GitHub Remote | Recommended Repo | Source-of-Truth Status | Next Action |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| project-os | `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of` | operating/status repo | No app code | Status checks only | Yes, branch `codex/heater-onboarding-status` | `https://github.com/BohyungKim/project-os.git` | `project-os` | Established; PR #4 merged to `main` | Review this heater onboarding status PR after validation |
| planner-workload-analyzer | `C:\Users\JohnKim\Documents\New project` | real app/code project | Yes, Python package under `src/planner_analyzer` | Yes, `python -m pytest` passed 7 tests | Yes, branch `main`, remote commit `7427048` | `https://github.com/BohyungKim/planner-workload-analyzer.git` | `planner-workload-analyzer` | Established; GitHub `main` is the source of truth | Onboard `heater-batch-selection` next |
| heater-batch-selection | `C:\Users\JohnKim\Documents\New project 2` | real app/code project | Yes, Python package under `src/heater_batch` | Yes, `python -m pytest` passed 9 tests | Yes, branch `main`, local commit `4f5eb1f` | None; target repo not found at `https://github.com/BohyungKim/heater-batch-selection.git` | `heater-batch-selection` | Local source-of-truth baseline prepared; GitHub repo still needed | John creates empty private GitHub repo, then Codex adds origin and pushes `main` |
| prg-supply-readiness-checker | `C:\Users\JohnKim\Documents\New project 3` | documentation/design project | No implementation code yet | No tests yet | Yes, no commits yet on `master` | None | `prg-supply-readiness-checker` | Not yet established | Create docs-first repo, then add sample data and validation tests |
| project-os legacy sync workspace | `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | operating/status repo | No app code | Status checks only | Yes, branch `docs/agents-guidelines-sync-mainbase` | `https://github.com/BohyungKim/project-os.git` | No separate repo recommended | Legacy/duplicate project-os workspace | Do not onboard separately; archive after John confirms it is no longer needed |

## Recommended Onboarding Order

1. `planner-workload-analyzer`
   - Best first real app repo candidate.
   - It has a clear README, Python package structure, `.gitignore`, config, source-of-truth files, and 7 passing tests.
   - Local baseline commit exists: `749ade2 docs: add source-of-truth onboarding files`.
   - Latest remote `main` commit: `7427048 docs: confirm GitHub source of truth`.
   - `origin` is configured and GitHub `main` is established as the source of truth.
   - Temporary branch `codex/source-of-truth-baseline` was deleted after `main` was updated.
2. `heater-batch-selection`
   - Also a real app candidate with 9 passing tests.
   - Local baseline commit exists: `4f5eb1f docs: add heater source-of-truth setup`.
   - Source-of-truth files and browser automation safety rules have been added locally.
   - Current blocker: `BohyungKim/heater-batch-selection` does not exist yet or is not accessible from this environment.
   - Slightly higher review risk because it includes Playwright-assisted NepConnect browser flow.
3. `prg-supply-readiness-checker`
   - Good docs-first repo candidate.
   - First implementation task should be sample data and validation tests, not Epicor write-back.
4. Legacy `agents-md-role-you-are-working`
   - Do not create a new repo.
   - Treat as historical `project-os` setup workspace.

## Current Risks

- `New project`, `New project 2`, and `New project 3` are placeholder folder names. John should confirm final project names before repo creation.
- `New project` now has a GitHub remote and `origin/main` is the stable source of truth.
- `New project 2` now has a local `main` commit, but no GitHub remote because the target repo was not found.
- `New project 3` has git initialized but no commits and no remote.
- `New project` contains a local `.env`; it was verified as ignored before the onboarding commit.
- `New project 2` includes browser automation; review safety constraints before making it a production workflow.
- `New project 3` is planning-only, so calling it an app repo would be premature.
- The legacy `agents-md-role-you-are-working` folder points to the same `project-os` remote and should not become a separate source of truth.

## Next Best Action

John should create the empty private GitHub repo `BohyungKim/heater-batch-selection`, then ask Codex to add it as `origin`, push `main`, and continue with `prg-supply-readiness-checker` only after the second repo is connected.
