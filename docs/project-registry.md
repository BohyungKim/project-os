# Project Registry

Updated: 2026-05-09 11:37 -04:00

Purpose: make `project-os` the central control tower for Codex and ChatGPT continuity. This file tracks where each currently accessible local project lives, what it appears to be, whether it already has its own GitHub source-of-truth repo, and the next safe action.

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
| project-os | `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of` | operating/status repo | No app code | Status checks only | Yes, branch `codex/correct-local-folder-mapping` | `https://github.com/BohyungKim/project-os.git` | `project-os` | Established; `main` is central registry truth | Review mapping correction PR after validation |
| planner-workload-analyzer | `C:\Users\JohnKim\Documents\New project` | real app/code project | Yes, Python package under `src/planner_analyzer` | Yes, `python -m pytest` previously passed 7 tests | Yes, branch `main`, local `HEAD` equals `origin/main` at `7427048` | `https://github.com/BohyungKim/planner-workload-analyzer.git` | `planner-workload-analyzer` | Established; current local folder is verified, preferred future folder is `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer` | Relocate by clean clone from GitHub after confirming no unpushed changes; do not manually move until John approves |
| heater-batch-selection | `C:\Users\JohnKim\Documents\New project 2` | real app/code project | Yes, Python package under `src/heater_batch` | Yes, `python -m pytest` previously passed 9 tests | Yes, branch `main` | `https://github.com/BohyungKim/heater-batch-selection.git` | `heater-batch-selection` | Established; GitHub `main` is the source of truth | Continue to keep browser automation manual-review / safe dry-run only |
| prg-contracts | `C:\Users\JohnKim\Documents\New project 3` | contract/schema repo | No application code | Yes, schema sample validator | Yes, branch `main`, local `HEAD` equals `origin/main` at `3455ead` | `https://github.com/BohyungKim/prg-contracts.git` | `prg-contracts` | Established as a contract-only repo; do not replace with `PRG` as-is | Review `PRG` split decision before changing the local working-folder mapping |
| PRG folder audit | `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` | mixed PRG app/orchestrator plus contract docs | Yes, Python package under `src/prg`, Epicor client/API, scripts, templates | Yes, unit/integration tests under `tests` | No local `.git` repo found | None | Split before assigning to a repo | Not safe to force into `prg-contracts` as-is; folder also contains `.env` | Separate contract/schema material from app/dashboard/orchestrator logic before any repo remap |
| project-os legacy sync workspace | `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | operating/status repo | No app code | Status checks only | Yes, branch `docs/agents-guidelines-sync-mainbase` | `https://github.com/BohyungKim/project-os.git` | No separate repo recommended | Legacy/duplicate project-os workspace | Do not onboard separately; archive after John confirms it is no longer needed |

## PRG Folder Audit Summary

`C:\Users\JohnKim\Desktop\Bins\Projects\PRG` contains contract/schema material, but it is not contract-only.

Confirmed contents:

- Contract/schema docs: `docs\PRG_DATA_CONTRACT.md`, `docs\epicor_schema_notes.md`, `docs\factors.md`, `docs\architecture.md`, `docs\decisions\001-factor-plugin-pattern.md`.
- App/orchestrator/dashboard code: `src\prg\api.py`, `src\prg\epicor\client.py`, factor modules, `scripts\daily_scan.py`, `scripts\run_against_job.py`, HTML/CSS templates under `src\prg\templates`.
- Roadmap/process docs: `PRG_ClaudeCode_Implementation_Guide.md`, `docs\PRG_CHECKLIST.md`, `docs\HUMAN_IN_THE_LOOP_POLICY.md`.
- Tests: unit and integration tests under `tests`.
- Git: no `.git` repo found in `PRG`.
- Remote URL: none, because the folder is not currently a Git repository.
- Secrets/local config: `.env` exists at the folder root. Contents were not read.

Conclusion:

- `PRG` should not become the local working folder for `BohyungKim/prg-contracts.git` as-is.
- If John wants PRG contract material in `prg-contracts`, split/extract only the contract/schema docs and examples into the existing contract-only repo through a reviewed PR.
- App/orchestrator/dashboard logic should remain separate or get its own repo mapping.

## Planner Local Path Cleanup

Current verified folder:

- `C:\Users\JohnKim\Documents\New project`

Preferred future folder:

- `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`

Audit result:

- `origin` is `https://github.com/BohyungKim/planner-workload-analyzer.git`.
- Local `HEAD` equals `origin/main` at `7427048`.
- Ahead/behind relative to `origin/main`: `0/0`.
- Working tree is clean.
- `.env` exists locally but is ignored; `.env.example` is tracked.

Safe cleanup plan:

1. Do not move or rename the current folder yet.
2. Clone `https://github.com/BohyungKim/planner-workload-analyzer.git` into `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`.
3. Run tests from the cloned folder.
4. Compare any local-only files John still needs, especially ignored `.env`.
5. After John confirms the clone works, archive or delete the old placeholder folder in a separate explicit cleanup task.

## Current Risks

- `PRG` is a mixed workspace and contains a local `.env`; treating it as contract-only could accidentally mix app logic and local config into `prg-contracts`.
- `planner-workload-analyzer` still lives in a placeholder folder name even though its GitHub source of truth is established.
- Existing `prg-contracts` is contract-only at `C:\Users\JohnKim\Documents\New project 3`; changing that mapping requires John review because it would replace a verified source-of-truth folder with a non-git mixed folder.

## Next Best Action

John should review whether PRG should be split into:

- contract/schema material that belongs in `BohyungKim/prg-contracts`, and
- app/orchestrator/dashboard code that belongs in a separate PRG application repo.
