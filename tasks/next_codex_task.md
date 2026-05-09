# Next Codex Task

## Objective

Finish connecting `C:\Users\JohnKim\Documents\New project 2` to GitHub as `BohyungKim/heater-batch-selection`.

## Scope

- Wait until John creates the empty private GitHub repo:
  - `https://github.com/BohyungKim/heater-batch-selection`
- Review/merge `project-os` PR #5 if the registry status update is acceptable:
  - `https://github.com/BohyungKim/project-os/pull/5`
- In `C:\Users\JohnKim\Documents\New project 2`, add the GitHub remote as `origin`.
- Push local `main` to `origin` if the remote is empty.
- If remote `main` has unrelated history, stop and report before any overwrite.
- Open a PR if applicable.
- Re-run tests and secret checks before push if any files changed.
- Update app state/report/task files after push.
- Update `project-os` registry/status files after the app repo is connected.
- Open a separate `project-os` registry update PR.

## Out Of Scope

- Creating the GitHub repo automatically unless John explicitly provides an authenticated workflow.
- Onboarding `prg-supply-readiness-checker` before the second app repo is connected.
- Changing application logic.
- Automating login, purchasing, submission, or production-impacting browser actions.
- Merging any app or `project-os` PR automatically.

## Files To Inspect

In `C:\Users\JohnKim\Documents\New project 2`:

- `.gitignore`
- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
- `pyproject.toml`
- `src/heater_batch/*`
- `src/heater_batch/adapters/*`
- `tests/*`

In `project-os`:

- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `reports/latest_execution_report.md`

## Files To Modify

In `New project 2` only if needed after remote creation:

- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

In `project-os`:

- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `docs/realtime-repo-status.md`
- `reports/latest_execution_report.md`
- `state/current_state.md`
- `state/current_state.json`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

## Acceptance Criteria

- `origin` in `New project 2` points to `https://github.com/BohyungKim/heater-batch-selection.git`.
- Local `main` is pushed to GitHub or a safe setup branch is created if remote history is not empty.
- No secrets, browser artifacts, or local-only files are tracked or pushed.
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

- heater-batch-selection source-of-truth status
- GitHub repo URL or repo creation blocker
- branch name
- test result
- changed files
- safety risks
- project-os PR link
- next recommended project to onboard
