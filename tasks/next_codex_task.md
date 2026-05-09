# Next Codex Task

## Objective

Review existing Job BOM Comparator app/product changes for the first feature PR.

## Scope

- Use canonical project root:
  - `C:\Users\JohnKim\Desktop\Bins\Projects`
- Local folder:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`
- Use existing local branch:
  - `codex/source-of-truth-onboarding`
- Confirm `origin` points to:
  - `https://github.com/BohyungKim/job-bom-comparator.git`
- Confirm `main` exists and use it as the stable base.
- Confirm whether GitHub default branch has been switched to `main`.
- Review existing modified/untracked app/product files before stable baseline promotion.

## Out Of Scope

- Reading `.env` contents.
- Discarding local changes.
- Changing GitHub default branch without John review if the tooling is not explicit.
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
- Job BOM Comparator `main` is confirmed on GitHub.
- Dirty app/product changes are classified into safe feature scope.
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
