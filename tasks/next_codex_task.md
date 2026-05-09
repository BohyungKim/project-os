# Next Codex Task

## Objective

Finish connecting `C:\Users\JohnKim\Documents\New project` to GitHub as `BohyungKim/planner-workload-analyzer`.

## Scope

- Wait until John creates the empty private GitHub repo:
  - `https://github.com/BohyungKim/planner-workload-analyzer`
- Review/merge `project-os` PR #4 if the registry status update is acceptable:
  - `https://github.com/BohyungKim/project-os/pull/4`
- In `C:\Users\JohnKim\Documents\New project`, add the GitHub remote as `origin`.
- Push local `main` to `origin`.
- Open a PR if applicable.
- Re-run tests and secret checks before push if any files changed.
- Update app state/report/task files after push.
- Update `project-os` registry/status files after the app repo is connected.
- Open a separate `project-os` registry update PR.

## Out Of Scope

- Creating the GitHub repo automatically unless John explicitly provides an authenticated workflow.
- Onboarding `heater-batch-selection` before the first app repo is connected.
- Onboarding `prg-supply-readiness-checker` before the first app repo is connected.
- Changing application logic.
- Merging any app or `project-os` PR automatically.

## Files To Inspect

In `C:\Users\JohnKim\Documents\New project`:

- `.gitignore`
- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
- `pyproject.toml`
- `tests/*`

In `project-os`:

- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `reports/latest_execution_report.md`

## Files To Modify

In `New project` only if needed after remote creation:

- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

In `project-os`:

- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `reports/latest_execution_report.md`
- `state/current_state.md`
- `state/current_state.json`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

## Acceptance Criteria

- `origin` in `New project` points to `https://github.com/BohyungKim/planner-workload-analyzer.git`.
- Local `main` is pushed to GitHub.
- No secrets or local-only files are tracked or pushed.
- Tests pass.
- App source-of-truth files reflect the pushed status.
- `project-os` registry reflects the connected app repo.
- No automatic merge is performed.

## Validation Command

```powershell
git status --short --branch
git remote -v
python -m pytest
Get-Content state/current_state.json | ConvertFrom-Json
git diff --check
```

## Report-Back Format

- app project repo status
- branch name
- remote URL
- test result
- changed files
- whether GitHub repo creation is still needed from John
- app PR link if created
- project-os registry update PR link if created
- next project to onboard
