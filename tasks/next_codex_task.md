# Next Codex Task

## Objective

Create the PR from the `main`-based branch and complete the Notion update with the PR link.

## Scope

- Push `docs/agents-guidelines-sync-mainbase`.
- Create a PR if GitHub access is available.
- Update the Notion project page with the final PR link.
- Ask John to confirm that `BohyungKim/project-os` and the selected Notion page are the intended long-term targets.

## Out of Scope

- Application feature work.
- Refactoring the AGENTS rules beyond review feedback.
- Modifying credentials, tokens, API keys, or production config.
- Force-pushing or deleting the original `docs/agents-guidelines-sync` branch.

## Files to Inspect

- `AGENTS.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `decisions/decision_log.md`
- `tasks/next_codex_task.md`

## Files to Modify

- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md` if a new workflow decision is made.

## Acceptance Criteria

- `git remote -v` shows `https://github.com/BohyungKim/project-os.git`.
- `docs/agents-guidelines-sync-mainbase` is pushed.
- PR is opened against `main` or exact blocker is documented.
- Notion project page is updated directly with the final run summary and PR link.
- Required state files reflect the latest verified state.

## Validation Command

```powershell
git status --short --branch
git remote -v
git log --oneline -1
```

## Report-Back Format

Use the required final structure from `AGENTS.md`.

