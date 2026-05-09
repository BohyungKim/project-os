# Next Codex Task

## Objective

Audit and prepare `Job BOM Comparator Agent` for GitHub source-of-truth onboarding.

## Scope

- Use canonical project root:
  - `C:\Users\JohnKim\Desktop\Bins\Projects`
- Local folder:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`
- Inspect git status, `.gitignore`, tracked files, modified files, untracked files, and remote status.
- Confirm `.env` and local-only files are not tracked.
- Decide whether the local folder should become:
  - `BohyungKim/job-bom-comparator`, or
  - another repo name John approves.
- Prepare source-of-truth files only after the working tree is understood.

## Out Of Scope

- Reading `.env` contents.
- Discarding local changes.
- Adding a GitHub remote before safety audit.
- Pushing code before John approves the target repo.
- Changing application logic.
- Merging any PR automatically.

## Files To Inspect

- `.gitignore`
- `README.md`
- `AGENTS.md`
- `requirements.txt`
- `src/`
- `tests/`
- `docs/`

## Files To Modify

Only after audit:

- `.gitignore` if needed
- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

## Acceptance Criteria

- Working tree status is clearly summarized.
- Secrets/local-only files are confirmed untracked.
- GitHub remote status is confirmed.
- Target repo name is recommended.
- No code is pushed until John approves.

## Validation Command

```powershell
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" remote -v
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-files
```

## Report-Back Format

- local folder
- branch
- remote status
- modified files summary
- untracked files summary
- secret/local-only tracking result
- recommended GitHub repo name
- whether ready for onboarding
