# Next Codex Task

## Objective

Onboard the third detected project: `prg-supply-readiness-checker`.

## Scope

- Use local folder:
  - `C:\Users\JohnKim\Documents\New project 3`
- Target GitHub repo:
  - `BohyungKim/prg-supply-readiness-checker`
- Treat it as a documentation/design-first project.
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
- Add docs if useful:
  - `docs/implementation-roadmap.md`
  - `docs/data-contract-draft.md`
- Connect/push only if the GitHub repo exists and remote history is safe.
- Update `project-os` registry after completion.

## Special Safety Rule

This is a docs-first project, not a production app yet. Do not pretend implementation exists. Do not add Epicor write-back logic.

## Out Of Scope

- Writing production app logic.
- Adding Epicor write-back logic.
- Claiming tests pass if no tests exist.
- Pushing secrets or generated local files.
- Merging any PR automatically.

## Files To Inspect

- `C:\Users\JohnKim\Documents\New project 3\README.md`
- `C:\Users\JohnKim\Documents\New project 3\docs\`
- `.gitignore` if present

## Files To Modify

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
- `docs/implementation-roadmap.md`
- `docs/data-contract-draft.md` if useful
- `.gitignore` if needed
- `project-os` registry files after completion

## Acceptance Criteria

- `prg-supply-readiness-checker` has docs-first source-of-truth files.
- No implementation is claimed unless code exists.
- No secrets or local-only files are tracked.
- GitHub repo connection status is clearly recorded.
- `project-os` registry is updated.
- No app logic is changed.
- No automatic merge is performed.

## Validation Command

```powershell
git status --short --branch
git remote -v
Get-Content state/current_state.json | ConvertFrom-Json
git diff --check
```

## Report-Back Format

- project name
- branch name
- remote URL/status
- validation result
- changed files
- source-of-truth status
- project-os PR link
- next recommended project
