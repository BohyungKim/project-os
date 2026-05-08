# Next Codex Task

## Objective

Connect this operating repo to GitHub so it can become a true shared source of truth between ChatGPT and Codex.

## Scope

- Confirm the intended GitHub owner and repo name with John.
- Add the GitHub remote as `origin`.
- Push `codex/source-of-truth-status-setup` after `origin` exists.
- Open a pull request against `main` if PR tooling is available.
- Update state/report/task files after the push attempt.

## Out Of Scope

- Merging to `main`.
- Changing application logic.
- Publishing unrelated local project folders.
- Moving this repo into `project-os` without John approval.

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

- `git remote -v` shows the intended GitHub repo as `origin`.
- `git push -u origin codex/source-of-truth-status-setup` succeeds.
- A PR exists or the exact PR creation blocker is documented.
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
