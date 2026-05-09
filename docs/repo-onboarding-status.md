# Repo Onboarding Status

Updated: 2026-05-09 11:35 -04:00

## Summary

| Priority | Project | Recommended GitHub Repo | Onboarding Status | Blocker | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `BohyungKim/project-os` | Established | None for registry foundation; PR #5 is merged | Review this `prg-contracts` registry update PR |
| 1 | planner-workload-analyzer | `BohyungKim/planner-workload-analyzer` | Established | None | Use GitHub `main` as source of truth |
| 2 | heater-batch-selection | `BohyungKim/heater-batch-selection` | Established | Browser automation safety review remains ongoing | Use GitHub `main` as source of truth; keep browser actions dry-run/manual-review |
| 3 | prg-contracts | `BohyungKim/prg-contracts` | Established | None for contract repo baseline | Integrate first feeder repo with PRGCase-compatible output |
| N/A | project-os legacy sync workspace | None | Do not onboard | Duplicate project-os workspace | Archive after John confirmation |

## First Project Onboarded

`planner-workload-analyzer`

Result:
- GitHub repo: `https://github.com/BohyungKim/planner-workload-analyzer.git`.
- Latest GitHub `main` commit: `7427048 docs: confirm GitHub source of truth`.
- Tests: `python -m pytest` passed 7 tests.
- Status: established.

## Second Project Onboarded

`heater-batch-selection`

Result:
- GitHub repo: `https://github.com/BohyungKim/heater-batch-selection.git`.
- Latest GitHub `main` commit: `6e32db7 docs: confirm heater GitHub source of truth`.
- Tests: `python -m pytest` passed 9 tests.
- Browser automation status: manual-review / safe dry-run only.
- Status: established.

## Third Repo Onboarded

`prg-contracts`

Result:
- Local folder: `C:\Users\JohnKim\Documents\New project 3`.
- Branch: `main`.
- GitHub repo: `https://github.com/BohyungKim/prg-contracts.git`.
- Latest GitHub `main` commit: `3455eaddc9413acf12f195cd58ad04deaef9a4d0`.
- Validation: `python tools/validate_prg_case.py examples/*.json` passed for 4 sample PRGCase files.
- Status: established.

Scope:
- Defines shared PRG / Manufacturing Copilot contracts only.
- Does not build the PRG dashboard.
- Does not build the POBTO Material Readiness Checker.
- Does not add Epicor write-back logic.
- Does not add production-impacting automation.
- Does not add feeder-specific detection logic.

## Exact Next Prompt For First Feeder Integration

```text
Use project-os main as the central registry.

Use prg-contracts main as the PRG / Manufacturing Copilot contract source of truth.

Now integrate the first feeder repo with PRGCase-compatible output.

Recommended first feeder:
job-bom-comparator

Task:
Inspect the feeder repo and add the smallest safe PRGCase-compatible export or report output using prg-contracts as the contract reference.

Important:
- Do not modify prg-contracts unless a schema change request is needed.
- Do not invent incompatible case fields.
- Do not add Epicor write-back logic.
- Do not add production-impacting automation.
- Do not merge automatically.

Before finishing, update the feeder repo state/report/task files and update project-os registry if project status changed.
```

## Notes

- Do not create GitHub repos automatically until John confirms names and ownership.
- Do not push app code until `.env`/secret safety has been verified.
- Do not merge any onboarding PR without John/ChatGPT review.
