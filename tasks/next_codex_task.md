# Next Codex Task

## Objective

Resolve `planner-workload-analyzer` remote `main` history so GitHub `main` can become the app source of truth.

## Scope

- Use John's selected history policy:
  - Preferred: delete/recreate `BohyungKim/planner-workload-analyzer` as a truly empty repo, then push local `main`.
  - Alternative: explicitly approve replacing remote `main` with local `main`.
- Reconfirm no secrets or local-only files are tracked.
- Re-run tests.
- Push local `main` only after the history policy is clear.
- Update app state/report/task files after successful `origin/main` push.
- Update `project-os` registry after app `origin/main` is established.
- Keep PR #4 updated or open a follow-up `project-os` PR if needed.

## Out Of Scope

- Changing app logic.
- Force pushing without explicit John approval.
- Merging unrelated histories without explicit John approval.
- Onboarding `heater-batch-selection` before this first app has a stable `origin/main`.
- Merging any PR automatically.

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

In `project-os`:

- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `reports/latest_execution_report.md`

## Files To Modify

In app repo:

- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md` if the selected history policy is new

In `project-os`:

- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `docs/realtime-repo-status.md`
- `reports/latest_execution_report.md`
- `state/current_state.md`
- `state/current_state.json`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md` if needed

## Acceptance Criteria

- `origin/main` in `planner-workload-analyzer` contains the app baseline.
- `origin/main` is the stable source of truth.
- Tests pass.
- No secrets or local-only files are tracked.
- App source-of-truth files reflect the final pushed status.
- `project-os` registry reflects the connected source-of-truth repo.
- No automatic merge is performed.

## Validation Command

```powershell
git status --short --branch
git remote -v
git log -1 --oneline
git ls-remote origin main
python -m pytest
Get-Content state/current_state.json | ConvertFrom-Json
git diff --check
```

## Report-Back Format

- planner-workload-analyzer GitHub repo URL
- branch pushed
- latest commit hash
- test result
- source-of-truth status
- project-os PR link
- next project to onboard
