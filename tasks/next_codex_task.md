# Next Codex Task

## Objective

Onboard the second detected project: `heater-batch-selection`.

## Scope

- Use local folder:
  - `C:\Users\JohnKim\Documents\New project 2`
- Target GitHub repo:
  - `BohyungKim/heater-batch-selection`
- Inspect project structure and git state.
- Verify no `.env`, credentials, tokens, API keys, passwords, or local-only files are tracked.
- Add/update source-of-truth files:
  - `AGENTS.md`
  - `README.md`
  - `state/current_state.md`
  - `state/current_state.json`
  - `reports/latest_execution_report.md`
  - `tasks/next_codex_task.md`
  - `decisions/decision_log.md`
- Run tests.
- Connect/push only if the GitHub repo exists and remote history is safe.
- Update `project-os` registry after completion.

## Special Safety Rule

This project may include Playwright/browser automation. Do not automate login, purchasing, submission, or production-impacting actions. Keep browser automation in manual-review or safe dry-run mode unless John explicitly approves otherwise.

## Out Of Scope

- Changing application logic.
- Running production-impacting browser actions.
- Pushing secrets or generated local files.
- Merging any PR automatically.

## Files To Inspect

- `C:\Users\JohnKim\Documents\New project 2\.gitignore`
- `C:\Users\JohnKim\Documents\New project 2\README.md`
- `C:\Users\JohnKim\Documents\New project 2\pyproject.toml`
- `C:\Users\JohnKim\Documents\New project 2\src\`
- `C:\Users\JohnKim\Documents\New project 2\tests\`

## Files To Modify

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
- `.gitignore` if needed
- `project-os` registry files after completion

## Acceptance Criteria

- `heater-batch-selection` has project source-of-truth files.
- Tests pass.
- No secrets or local-only files are tracked.
- GitHub repo connection status is clearly recorded.
- `project-os` registry is updated.
- No app logic is changed.
- No production-impacting browser automation is run.

## Validation Command

```powershell
git status --short --branch
git remote -v
python -m pytest
Get-Content state/current_state.json | ConvertFrom-Json
git diff --check
```

## Report-Back Format

- project name
- branch name
- remote URL/status
- test result
- changed files
- source-of-truth status
- project-os PR link
- next recommended project
