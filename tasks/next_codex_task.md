# Next Codex Task

## Objective

Connect `Job BOM Comparator Agent` to GitHub after John creates the empty private repo.

## Scope

- Use canonical project root:
  - `C:\Users\JohnKim\Desktop\Bins\Projects`
- Local folder:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`
- Use existing local branch:
  - `codex/source-of-truth-onboarding`
- Confirm John created:
  - `https://github.com/BohyungKim/job-bom-comparator.git`
- Add `origin` only if it is missing.
- Push the prepared branch or main exactly as John approves.
- Update project-os after the app repo push.

## Out Of Scope

- Reading `.env` contents.
- Discarding local changes.
- Creating the GitHub repo from Codex unless John explicitly asks and the GitHub tooling supports it.
- Pushing before the target empty private repo exists.
- Changing application logic.
- Merging any PR automatically.

## Files To Inspect

- `AGENTS.md`
- `.gitignore`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

## Files To Modify

- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
- project-os registry/status files after push

## Acceptance Criteria

- `origin` points to `https://github.com/BohyungKim/job-bom-comparator.git`.
- Prepared Job BOM Comparator branch/main is pushed without secrets.
- `origin/main` or the agreed onboarding branch is confirmed.
- Project-os registry files are updated in a PR.
- No PR is merged automatically.

## Validation Command

```powershell
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" remote -v
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-files
cd "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent"
.\.venv\Scripts\python.exe -B -m pytest
```

## Report-Back Format

- local folder
- branch
- remote status
- pushed branch or blocker
- secret/local-only tracking result
- test result
- project-os PR link
