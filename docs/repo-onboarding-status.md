# Repo Onboarding Status

Updated: 2026-05-09 11:09 -04:00

## Summary

| Priority | Project | Recommended GitHub Repo | Onboarding Status | Blocker | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `BohyungKim/project-os` | Established | None for registry foundation; PR #4 is merged | Review draft PR #5: `https://github.com/BohyungKim/project-os/pull/5` |
| 1 | planner-workload-analyzer | `BohyungKim/planner-workload-analyzer` | Established | None | Use GitHub `main` as source of truth |
| 2 | heater-batch-selection | `BohyungKim/heater-batch-selection` | Established | Browser automation safety review remains ongoing | Use GitHub `main` as source of truth |
| 3 | prg-supply-readiness-checker | `BohyungKim/prg-supply-readiness-checker` | Docs-first candidate | No code/tests yet | Onboard next as docs-first repo |
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
- Latest GitHub `main` commit: `6e32db7 docs: confirm heater GitHub source of truth`.
- Tests: `python -m pytest` passed 9 tests.
- GitHub repo: `https://github.com/BohyungKim/heater-batch-selection.git`.
- Browser automation status: manual-review / safe dry-run only.

Current blocker:
- None for `heater-batch-selection` source-of-truth setup.

John action required:
- Review/merge `project-os` PR #5 when satisfied.
- Prepare `BohyungKim/prg-supply-readiness-checker` when ready for the docs-first onboarding.

Then ask Codex:

```text
Now onboard the third detected project.

Local folder:
C:\Users\JohnKim\Documents\New project 3

Target GitHub repo:
BohyungKim/prg-supply-readiness-checker

This is a documentation/design-first project, not a production app yet.

Prepare it as a docs-first source-of-truth repo. Do not pretend implementation exists. Do not add Epicor write-back logic. Update project-os registry after completion. Do not merge automatically.
```

## Exact Next Prompt For Third Repo

```text
Now onboard the third detected project.

Local folder:
C:\Users\JohnKim\Documents\New project 3

Target GitHub repo:
BohyungKim/prg-supply-readiness-checker

This is a documentation/design-first project, not a production app yet.

Add AGENTS.md, source-of-truth state/report/task/decision files, README updates, docs/implementation-roadmap.md, and docs/data-contract-draft.md if useful.
Do not pretend implementation exists.
Do not add Epicor write-back logic.
Run validation checks, update project-os registry, push, and open PR.
Do not merge automatically.
```

## Notes

- Do not create GitHub repos automatically until John confirms names and ownership.
- Do not push app code until `.env`/secret safety has been verified.
- Do not merge any onboarding PR without John/ChatGPT review.
