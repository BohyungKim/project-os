# Repo Onboarding Status

Updated: 2026-05-09 10:56 -04:00

## Summary

| Priority | Project | Recommended GitHub Repo | Onboarding Status | Blocker | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `BohyungKim/project-os` | Established | None for registry foundation; PR #4 is merged | Review draft PR #5: `https://github.com/BohyungKim/project-os/pull/5` |
| 1 | planner-workload-analyzer | `BohyungKim/planner-workload-analyzer` | Established | None | Use GitHub `main` as source of truth |
| 2 | heater-batch-selection | `BohyungKim/heater-batch-selection` | Local baseline prepared | GitHub repo not found/connected; browser automation safety review needed | John creates empty private repo, then Codex adds origin and pushes `main` |
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
- Create/connect `BohyungKim/heater-batch-selection` when ready for the second onboarding.

## Second Project Onboarding Status

`heater-batch-selection`

Result:
- Local folder: `C:\Users\JohnKim\Documents\New project 2`.
- Branch: `main`.
- Local commit: `4f5eb1f docs: add heater source-of-truth setup`.
- Tests: `python -m pytest` passed 9 tests.
- Target repo check: `https://github.com/BohyungKim/heater-batch-selection.git` returned repository not found.
- Browser automation status: manual-review / safe dry-run only.

Current blocker:
- GitHub repo does not exist or is not accessible yet.

John action required:
- Create an empty private GitHub repo at `https://github.com/BohyungKim/heater-batch-selection`.
- Use Owner `BohyungKim`.
- Use Repository name `heater-batch-selection`.
- Do not initialize with README, `.gitignore`, or license.

Then ask Codex:

```text
I created the GitHub repo:
https://github.com/BohyungKim/heater-batch-selection.git

Continue from C:\Users\JohnKim\Documents\New project 2.
Add this remote as origin, push main or a safe setup branch, and open a PR if applicable.
Do not merge.
After pushing, update the project-os registry files and open a separate project-os PR.
Before finishing, update the state/report/task files so ChatGPT can understand the latest project status from GitHub without reading the entire codebase.
```

## Exact Next Prompt For Repo Connection

```text
Use C:\Users\JohnKim\Documents\New project 2.
Target remote:
https://github.com/BohyungKim/heater-batch-selection.git

Confirm no secrets are tracked, run tests, add origin, and push local main if the remote is empty.
If remote main has unrelated history, stop and report it before any overwrite.
Do not automate login, purchasing, submission, or production-impacting browser actions.
Update heater-batch-selection state/report/task files, then update project-os registry.
```

## Notes

- Do not create GitHub repos automatically until John confirms names and ownership.
- Do not push app code until `.env`/secret safety has been verified.
- Do not merge any onboarding PR without John/ChatGPT review.
