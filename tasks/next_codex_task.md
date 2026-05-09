# Next Codex Task

## Objective

Review or promote the pushed Job BOM Comparator source-of-truth branch.

## Scope

- Use canonical project root:
  - `C:\Users\JohnKim\Desktop\Bins\Projects`
- Local folder:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`
- Use existing local branch:
  - `codex/source-of-truth-onboarding`
- Confirm `origin` points to:
  - `https://github.com/BohyungKim/job-bom-comparator.git`
- Confirm remote branch:
  - `codex/source-of-truth-onboarding`
- Decide whether to promote the pushed branch to `main` or create a separate `main` base.
- Review existing modified/untracked app/product files before stable baseline promotion.

## Out Of Scope

- Reading `.env` contents.
- Discarding local changes.
- Promoting to `main` without John approval.
- Rewriting history without explicit approval.
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
- Prepared Job BOM Comparator branch is confirmed on GitHub.
- Stable `main` path is selected by John.
- Project-os registry files are updated in a PR.
- No PR is merged automatically.

## Validation Command

```powershell
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" remote -v
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-files
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-remote --heads origin
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
