# Repo Onboarding Status

Updated: 2026-05-08 19:36 -04:00

## Summary

| Priority | Project | Recommended GitHub Repo | Onboarding Status | Blocker | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `BohyungKim/project-os` | Established | Registry PR needs review | Review this PR and merge if acceptable |
| 1 | planner-workload-analyzer | `BohyungKim/planner-workload-analyzer` | Ready for repo onboarding | GitHub repo not created/connected | Create/connect private repo, then add project source-of-truth files |
| 2 | heater-batch-selection | `BohyungKim/heater-batch-selection` | Ready after planner onboarding | GitHub repo not created/connected; browser automation safety review needed | Onboard after planner project |
| 3 | prg-supply-readiness-checker | `BohyungKim/prg-supply-readiness-checker` | Docs-first candidate | No code/tests yet | Add source-of-truth files, then sample data and validation tests |
| N/A | project-os legacy sync workspace | None | Do not onboard | Duplicate project-os workspace | Archive after John confirmation |

## First Project To Onboard

`planner-workload-analyzer`

Reason:
- It is a real app/code project.
- It already has `src/`, `tests/`, config, and README.
- `python -m pytest` passed 7 tests.
- It has lower operational risk than the browser-assisted heater batch project.

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
