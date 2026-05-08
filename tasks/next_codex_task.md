# Next Codex Task

## Objective

Onboard `C:\Users\JohnKim\Documents\New project` as the first real project source-of-truth repo named `planner-workload-analyzer`.

## Scope

- Inspect `C:\Users\JohnKim\Documents\New project`.
- Confirm git branch, commit state, and remote state.
- Confirm `.env` and local-only files are ignored and not tracked.
- Add project-level source-of-truth files:
  - `AGENTS.md`
  - `state/current_state.md`
  - `state/current_state.json`
  - `reports/latest_execution_report.md`
  - `tasks/next_codex_task.md`
  - `decisions/decision_log.md`
- Update README only for repo onboarding clarity if needed.
- Run tests.
- Commit on a feature branch.

## Out Of Scope

- Creating the GitHub repo without John confirmation.
- Pushing app code before a remote exists.
- Changing application logic.
- Merging to `main`.

## Files To Inspect

- `README.md`
- `.gitignore`
- `.env.example`
- `pyproject.toml`
- `config/planner_sources.yaml`
- `src/planner_analyzer/*`
- `tests/*`

## Files To Modify

- `AGENTS.md`
- `README.md` if needed
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
- `.gitignore` only if secret/local exclusions are incomplete

## Acceptance Criteria

- No `.env`, credentials, tokens, API keys, generated data, or reports are tracked.
- Tests pass.
- Source-of-truth files exist.
- The exact GitHub remote needed is reported if no remote exists.
- No app logic is changed.

## Validation Command

```powershell
git status --short --branch
git remote -v
python -m pytest
```

## Report-Back Format

- project name
- branch name
- git remote status
- changed files
- test result
- whether it is ready to publish to GitHub
- exact next step for John
