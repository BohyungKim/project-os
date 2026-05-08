# Project Registry

Updated: 2026-05-08 19:36 -04:00

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
| project-os | `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of` | operating/status repo | No app code | Status checks only | Yes, branch `codex/central-project-registry` | `https://github.com/BohyungKim/project-os.git` | `project-os` | Established after PR #2 merge | Review and merge this registry PR after validation |
| planner-workload-analyzer | `C:\Users\JohnKim\Documents\New project` | real app/code project | Yes, Python package under `src/planner_analyzer` | Yes, `python -m pytest` passed 7 tests | Yes, no commits yet on `master` | None | `planner-workload-analyzer` | Not yet established | Onboard first as its own private GitHub repo |
| heater-batch-selection | `C:\Users\JohnKim\Documents\New project 2` | real app/code project | Yes, Python package under `src/heater_batch` | Yes, `python -m pytest` passed 9 tests | Yes, no commits yet on `master` | None | `heater-batch-selection` | Not yet established | Onboard after planner project; review browser automation safety carefully |
| prg-supply-readiness-checker | `C:\Users\JohnKim\Documents\New project 3` | documentation/design project | No implementation code yet | No tests yet | Yes, no commits yet on `master` | None | `prg-supply-readiness-checker` | Not yet established | Create docs-first repo, then add sample data and validation tests |
| project-os legacy sync workspace | `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | operating/status repo | No app code | Status checks only | Yes, branch `docs/agents-guidelines-sync-mainbase` | `https://github.com/BohyungKim/project-os.git` | No separate repo recommended | Legacy/duplicate project-os workspace | Do not onboard separately; archive after John confirms it is no longer needed |

## Recommended Onboarding Order

1. `planner-workload-analyzer`
   - Best first real app repo candidate.
   - It has a clear README, Python package structure, `.gitignore`, config, and 7 passing tests.
   - Risk to check first: local `.env` exists and must never be committed.
2. `heater-batch-selection`
   - Also a real app candidate with 9 passing tests.
   - Slightly higher review risk because it includes Playwright-assisted NepConnect browser flow.
3. `prg-supply-readiness-checker`
   - Good docs-first repo candidate.
   - First implementation task should be sample data and validation tests, not Epicor write-back.
4. Legacy `agents-md-role-you-are-working`
   - Do not create a new repo.
   - Treat as historical `project-os` setup workspace.

## Current Risks

- `New project`, `New project 2`, and `New project 3` are placeholder folder names. John should confirm final project names before repo creation.
- The app candidates have git initialized but no commits and no remotes.
- `New project` contains a local `.env`; verify it is ignored before any commit.
- `New project 2` includes browser automation; review safety constraints before making it a production workflow.
- `New project 3` is planning-only, so calling it an app repo would be premature.
- The legacy `agents-md-role-you-are-working` folder points to the same `project-os` remote and should not become a separate source of truth.

## Next Best Action

After this registry PR is reviewed, onboard `C:\Users\JohnKim\Documents\New project` as `BohyungKim/planner-workload-analyzer`.
