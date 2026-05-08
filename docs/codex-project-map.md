# Codex Project Map

Updated: 2026-05-08 19:36 -04:00

## Control Tower Layout

```text
BohyungKim/project-os
  central control tower
  project registry
  onboarding status
  shared AGENTS.md template
  status/report/task conventions

BohyungKim/planner-workload-analyzer
  future real app repo
  current local folder: C:\Users\JohnKim\Documents\New project

BohyungKim/heater-batch-selection
  future real app repo
  current local folder: C:\Users\JohnKim\Documents\New project 2

BohyungKim/prg-supply-readiness-checker
  future docs-first or app repo
  current local folder: C:\Users\JohnKim\Documents\New project 3
```

## Project Relationships

### project-os

Role:
- Central registry and operating layer.
- Does not own application code.
- Tracks which project repo is the source of truth for each initiative.

ChatGPT entry point:
- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `reports/latest_execution_report.md`

### planner-workload-analyzer

Role:
- First recommended real project repo to onboard.
- Read-only Microsoft Planner workload analyzer.

Why first:
- Clear Python package.
- Existing README.
- Existing `.gitignore`.
- Tests pass.
- Lower operational risk than browser-assisted workflows.

Expected future repo:
- `BohyungKim/planner-workload-analyzer`

### heater-batch-selection

Role:
- Real Python app candidate for internal heater batch selection.

Why second:
- Tests pass and structure is clear.
- Includes browser automation through Playwright/NepConnect, so review risk is higher.

Expected future repo:
- `BohyungKim/heater-batch-selection`

### prg-supply-readiness-checker

Role:
- PRG sub-system design/planning repo.

Why later:
- No implementation code or tests yet.
- Best next step is sample data and validation tests.

Expected future repo:
- `BohyungKim/prg-supply-readiness-checker`

### project-os legacy sync workspace

Role:
- Historical setup workspace for project-os operating rules.

Action:
- Do not turn this into a separate repo.
- Keep only until John confirms it is safe to archive.

## How John Should Ask ChatGPT Later

```text
Use project-os as the central registry.
Then use planner-workload-analyzer current_state.md as the project source of truth.
Tell me the current status and next best action.
```

## Required Per-Project Source-Of-Truth Files

Every real project repo should contain:

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
