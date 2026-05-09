# Project Registry

Updated: 2026-05-09 11:35 -04:00

Purpose: make `project-os` the central control tower for Codex and ChatGPT continuity. This file tracks where each currently accessible local project lives, what it appears to be, whether it already has its own GitHub source-of-truth repo, and the next safe onboarding or integration action.

## Control Tower Rule

`project-os` is not where all application code should live. It is the central registry and operating layer.

Each real project should eventually have its own GitHub repository with:

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

## Detected Projects

| Project | Local Folder | Classification | Has Code | Has Tests | Git | GitHub Remote | Recommended Repo | Source-of-Truth Status | Next Action |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| project-os | `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of` | operating/status repo | No app code | Status checks only | Yes, branch `codex/prg-contracts-onboarding-status` | `https://github.com/BohyungKim/project-os.git` | `project-os` | Established; PR #5 merged to `main` | Review this `prg-contracts` registry PR |
| planner-workload-analyzer | `C:\Users\JohnKim\Documents\New project` | real app/code project | Yes, Python package under `src/planner_analyzer` | Yes, `python -m pytest` passed 7 tests | Yes, branch `main`, remote commit `7427048` | `https://github.com/BohyungKim/planner-workload-analyzer.git` | `planner-workload-analyzer` | Established; GitHub `main` is the source of truth | Use as established app repo |
| heater-batch-selection | `C:\Users\JohnKim\Documents\New project 2` | real app/code project | Yes, Python package under `src/heater_batch` | Yes, `python -m pytest` passed 9 tests | Yes, branch `main`, remote commit `6e32db7` | `https://github.com/BohyungKim/heater-batch-selection.git` | `heater-batch-selection` | Established; GitHub `main` is the source of truth | Use as established app repo; keep browser automation safe dry-run/manual-review |
| prg-contracts | `C:\Users\JohnKim\Documents\New project 3` | shared contract repo | Contract validator only; no app/dashboard code | Yes, sample contract validation passed | Yes, branch `main`, remote commit `3455ead` | `https://github.com/BohyungKim/prg-contracts.git` | `prg-contracts` | Established; GitHub `main` is the source of truth | Integrate the first feeder repo with PRGCase output |
| project-os legacy sync workspace | `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | operating/status repo | No app code | Status checks only | Yes, branch `docs/agents-guidelines-sync-mainbase` | `https://github.com/BohyungKim/project-os.git` | No separate repo recommended | Legacy/duplicate project-os workspace | Do not onboard separately; archive after John confirms it is no longer needed |

## Established Source-Of-Truth Repos

1. `planner-workload-analyzer`
   - First real app repo.
   - GitHub `main` is established.
   - Latest known remote `main` commit: `7427048 docs: confirm GitHub source of truth`.
2. `heater-batch-selection`
   - Second real app repo.
   - GitHub `main` is established.
   - Latest known remote `main` commit: `6e32db7 docs: confirm heater GitHub source of truth`.
   - Safety rule remains: no automated login, purchasing, submission, or production-impacting browser action without explicit approval.
3. `prg-contracts`
   - PRG / Manufacturing Copilot shared contract repo.
   - GitHub `main` is established.
   - Latest known remote `main` commit: `3455eaddc9413acf12f195cd58ad04deaef9a4d0`.
   - Defines PRGCase schema, evidence schema, action schema, field registry, severity taxonomy, readiness area taxonomy, owner mapping, examples, schema change process, and validation tooling.
   - This is not the PRG dashboard, not the POBTO checker, and not a feeder-specific detection module.

## Next Integration Order

1. `job-bom-comparator`
   - Recommended first repo to integrate with `prg-contracts`.
   - Reason: comparator output is a natural first feeder and already has a sample PRGCase payload in `prg-contracts/examples/comparator_prg_case_sample.json`.
   - Next action: onboard or locate the repo, then add PRGCase-compatible export/output in a feature branch.
2. Transaction analysis feeder
   - Use `examples/transaction_prg_case_sample.json` as the initial contract reference.
3. POBTO readiness feeder
   - Use `examples/pobto_prg_case_sample.json`.
   - Keep this outside `prg-contracts`; do not build POBTO logic in the contract repo.
4. Closing review feeder
   - Use `examples/closing_prg_case_sample.json`.

## Current Risks

- `New project`, `New project 2`, and `New project 3` are still placeholder local folder names. John may want to rename local folders later for clarity.
- `heater-batch-selection` includes browser automation; keep NepConnect/Playwright in manual-review or safe dry-run mode.
- `prg-contracts` must stay contract-focused. Do not add dashboard, POBTO checker, Epicor write-back, production automation, or module-specific detection logic to that repo.
- The legacy `agents-md-role-you-are-working` folder points to the same `project-os` remote and should not become a separate source of truth.

## Next Best Action

Review this `project-os` PR, then integrate the first feeder repo, recommended: `job-bom-comparator`, with `prg-contracts` PRGCase-compatible output.
