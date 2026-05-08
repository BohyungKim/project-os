# Next Codex Task

## Objective

Connect this initialized workspace to the intended remote repository and Notion project page so future Codex sessions can push branches, open PRs, and update project state directly.

## Scope

- Confirm or configure `origin`.
- Confirm the target Notion project page URL or ID.
- Push `docs/agents-guidelines-sync`.
- Create a PR if GitHub access is available.
- Update state and report files with the remote and Notion details.

## Out of Scope

- Application feature work.
- Refactoring the AGENTS rules beyond review feedback.
- Modifying credentials, tokens, API keys, or production config.

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

- `git remote -v` shows the intended remote.
- Feature branch is pushed or the exact blocker is documented.
- PR is opened or exact PR creation commands are provided.
- Notion project page is updated directly or a copy-paste-ready update block is produced with the reason.
- Required state files reflect the latest verified state.

## Validation Command

```powershell
git status --short --branch
git remote -v
git log --oneline -1
```

## Report-Back Format

Use the required final structure from `AGENTS.md`.

