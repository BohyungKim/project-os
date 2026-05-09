# Next Codex Task

## Objective

Prepare a safe local folder cleanup for `planner-workload-analyzer`.

## Scope

- Use `project-os/main` as the central registry after this PR is merged.
- Use `planner-workload-analyzer/main` as the app source of truth.
- Current folder:
  - `C:\Users\JohnKim\Documents\New project`
- Preferred canonical folder:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`
- Clone from GitHub into the canonical folder.
- Run available tests from the clone.
- Confirm `.env` remains local-only and ignored.
- Report whether the old placeholder folder can become an archive candidate.

## Out Of Scope

- Deleting, moving, or renaming the old folder.
- Reading `.env` contents.
- Changing application logic.
- Pushing app code changes.
- Merging any PR automatically.

## Files To Inspect

- `project-os/docs/project-registry.md`
- `project-os/state/project_registry.json`
- `C:\Users\JohnKim\Documents\New project\.gitignore`
- `C:\Users\JohnKim\Documents\New project\README.md`
- `C:\Users\JohnKim\Documents\New project\state\current_state.md`

## Files To Modify

In `project-os`, if cleanup status changes:

- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `docs/codex-project-map.md`
- `docs/realtime-repo-status.md`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md` if a decision is made

Do not modify app code unless John explicitly requests it.

## Acceptance Criteria

- Canonical planner clone exists at `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`.
- Clone points to `https://github.com/BohyungKim/planner-workload-analyzer.git`.
- Clone branch is `main`.
- Tests pass from the clone.
- `.env` is not tracked or pushed.
- Old placeholder folder is only marked as archive candidate, not deleted.

## Validation Command

```powershell
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer" remote -v
python -m pytest
Get-Content state/project_registry.json | ConvertFrom-Json
git diff --check
```

## Report-Back Format

- canonical clone path
- branch name
- remote URL
- test result
- `.env` tracking result
- old folder archive recommendation
- project-os PR link if registry changed
