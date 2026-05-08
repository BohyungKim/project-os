# Next Codex Task

## Objective

Support John and ChatGPT review of draft PR #2, then make only requested follow-up documentation/status changes.

## Scope

- Review feedback on `https://github.com/BohyungKim/project-os/pull/2`.
- Make small documentation/status-structure adjustments if requested.
- Keep changes on `codex/source-of-truth-status-setup`.
- Do not merge to `main`.
- Update state/report/task/decision files after any follow-up.
- Push follow-up commits to `origin/codex/source-of-truth-status-setup`.

## Out Of Scope

- Merging to `main`.
- Changing application logic.
- Publishing unrelated local project folders.
- Moving this repo into `project-os` without John approval.
- Force-pushing or rewriting PR history unless John explicitly asks.

## Files To Inspect

- `AGENTS.md`
- `README.md`
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
- `decisions/decision_log.md` if John makes a repo ownership decision

## Acceptance Criteria

- Draft PR #2 remains open and reviewable.
- Any requested adjustments are committed and pushed.
- State/report/task files are updated with the verified result.
- `main` is not merged or modified directly.

## Validation Command

```powershell
git status --short --branch
git remote -v
git log --oneline -1
```

## Report-Back Format

Use the final output structure required by `AGENTS.md`, plus:

- branch name
- commit message
- changed files
- test result
- risks
- what ChatGPT should review next
- next recommended Codex prompt
