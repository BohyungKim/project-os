# Repo Onboarding Status

Updated: 2026-05-09 10:28 -04:00

## Summary

| Priority | Project | Recommended GitHub Repo | Onboarding Status | Blocker | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `BohyungKim/project-os` | Established | None for registry foundation; PR #3 is merged | Review draft PR #4: `https://github.com/BohyungKim/project-os/pull/4` |
| 1 | planner-workload-analyzer | `BohyungKim/planner-workload-analyzer` | Established | None | Use GitHub `main` as source of truth |
| 2 | heater-batch-selection | `BohyungKim/heater-batch-selection` | Ready for onboarding | GitHub repo not created/connected; browser automation safety review needed | Onboard next |
| 3 | prg-supply-readiness-checker | `BohyungKim/prg-supply-readiness-checker` | Docs-first candidate | No code/tests yet | Add source-of-truth files, then sample data and validation tests |
| N/A | project-os legacy sync workspace | None | Do not onboard | Duplicate project-os workspace | Archive after John confirmation |

## First Project Onboarded

`planner-workload-analyzer`

Reason:
- It is a real app/code project.
- It already has `src/`, `tests/`, config, README, and source-of-truth status files.
- `python -m pytest` passed 7 tests.
- Local baseline commit is `749ade2 docs: add source-of-truth onboarding files`.
- Latest GitHub `main` commit is `7427048 docs: confirm GitHub source of truth`.
- Temporary review branch `codex/source-of-truth-baseline` was deleted.
- It has lower operational risk than the browser-assisted heater batch project.

Current blocker:
- None for `planner-workload-analyzer` source-of-truth setup.

John action required:
- Review/merge `project-os` PR #4 when satisfied.
- Create/connect `BohyungKim/heater-batch-selection` when ready for the second onboarding.

Then ask Codex:

```text
Now onboard the second detected project.

Local folder:
C:\Users\JohnKim\Documents\New project 2

Target GitHub repo:
BohyungKim/heater-batch-selection

Special caution:
This project may include Playwright/browser automation. Do not automate login, purchasing, submission, or production-impacting actions. Keep browser automation in manual-review or safe dry-run mode unless explicitly approved.

Use the same source-of-truth setup, run tests, verify no secrets are tracked, prepare GitHub remote/push/PR, update project-os registry after completion, and do not merge automatically.
Do not merge anything automatically.
```

## Exact Next Prompt For First App Repo

```text
Onboard the local project folder "New project" as the first real project repo.

Target GitHub repo name:
planner-workload-analyzer

Task:
Prepare this project so it can become its own GitHub source-of-truth repo for ChatGPT and Codex.

Do not change application logic unless required for safe repo setup.

Required:
1. Inspect the project structure.
2. Confirm whether git is already initialized.
3. Confirm whether any GitHub remote exists.
4. Confirm no .env, credentials, tokens, API keys, or local-only files are tracked.
5. Improve .gitignore if needed.
6. Add AGENTS.md using the project-os standard.
7. Add:
   - state/current_state.md
   - state/current_state.json
   - reports/latest_execution_report.md
   - tasks/next_codex_task.md
   - decisions/decision_log.md
8. Update README.md with:
   - project purpose
   - how to run
   - how to test
   - main folders
   - known limitations
   - next actions
9. Run available tests.
10. Commit changes on a feature branch.
11. If GitHub remote exists, push the branch.
12. If GitHub remote does not exist, stop and tell John the exact repo URL needed.
13. Do not merge to main.

Before finishing, update the state/report/task files so ChatGPT can understand the latest project status from the GitHub repo without reading the entire codebase.
```

## Notes

- Do not create GitHub repos automatically until John confirms names and ownership.
- Do not push app code until `.env`/secret safety has been verified.
- Do not merge any onboarding PR without John/ChatGPT review.
