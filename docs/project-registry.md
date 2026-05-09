# Project Registry

Updated: 2026-05-09 11:52 -04:00

Purpose: make `project-os` the central control tower for Codex and ChatGPT continuity. This file tracks each currently accessible local project, its GitHub source-of-truth repo, and the safest local folder cleanup path.

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

| Project | Current Local Path | Preferred Canonical Local Path | Classification | GitHub Remote | Source-of-Truth Status | Relocation Status | Archive Candidate | Next Action |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| project-os | `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of` | Same as current for now | operating/status repo | `https://github.com/BohyungKim/project-os.git` | Established; `main` is central registry truth | No relocation needed now | No | Review PR #8: `https://github.com/BohyungKim/project-os/pull/8` |
| planner-workload-analyzer | `C:\Users\JohnKim\Documents\New project` | `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer` | real app/code project | `https://github.com/BohyungKim/planner-workload-analyzer.git` | Established; local `HEAD` equals `origin/main` at `7427048` | Safe to relocate later by clean clone from GitHub; do not manually move yet | Current placeholder folder becomes archive candidate only after clone/tests/.env review | Clone to canonical path in a separate explicit cleanup task |
| heater-batch-selection | `C:\Users\JohnKim\Documents\New project 2` | `C:\Users\JohnKim\Desktop\Bins\Projects\heater-batch-selection` | real app/code project | `https://github.com/BohyungKim/heater-batch-selection.git` | Established; GitHub `main` is source of truth at `6e32db7` | Relocation not audited yet; current path remains authoritative for now | Future archive candidate after clean clone and safety check | Keep browser automation manual-review / safe dry-run |
| prg-contracts | `C:\Users\JohnKim\Documents\New project 3` | `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts` after PRG split review | contract/schema repo | `https://github.com/BohyungKim/prg-contracts.git` | Established as contract-only; local `HEAD` equals `origin/main` at `3455ead` | Do not replace with `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` as-is | Current placeholder folder becomes archive candidate only after clean clone and PRG split review | Decide PRG split before changing mapping |
| PRG folder audit | `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` | Split target: contract material to `prg-contracts`, app/orchestrator material to a separate PRG app repo | mixed app/orchestrator plus contract docs | None; not a Git repo | Not established; audit-only | Split required before repo assignment | No; keep until split plan is approved | Prepare a split plan; do not push or read `.env` |
| project-os legacy sync workspace | `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | None | operating/status duplicate | `https://github.com/BohyungKim/project-os.git` | Legacy workspace; not a separate source of truth | Do not relocate; archive after John confirms | Yes, after John confirmation | Keep untouched until John approves archive |

## Audit Result

The useful local folder mapping corrections were preserved and moved onto a clean branch from current `project-os/main`:

- Branch: `codex/local-folder-mapping-audit`
- PR: `https://github.com/BohyungKim/project-os/pull/8`
- Source of previous useful work: `codex/correct-local-folder-mapping`
- Main base: `origin/main` after PR #6 merge

At the start of this task, there were no uncommitted local changes in the active worktree. The mapping audit changes already existed as committed branch work on `codex/correct-local-folder-mapping`, so they were preserved by carrying the useful content forward instead of discarding it.

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

Preferred canonical folder:

- `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`

Audit result:

- `origin` is `https://github.com/BohyungKim/planner-workload-analyzer.git`.
- Local `HEAD` equals `origin/main` at `7427048`.
- Ahead/behind relative to `origin/main`: `0/0`.
- Working tree is clean.
- `.env` exists locally but is ignored; `.env.example` is tracked.
- Preferred folder does not exist yet.

Safe cleanup plan:

1. Do not move or rename the current folder yet.
2. Clone `https://github.com/BohyungKim/planner-workload-analyzer.git` into `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`.
3. Run tests from the cloned folder.
4. Compare any local-only files John still needs, especially ignored `.env`.
5. After John confirms the clone works, archive or delete the old placeholder folder in a separate explicit cleanup task.

## Current Risks

- `PRG` is a mixed workspace and contains a local `.env`; treating it as contract-only could accidentally mix app logic and local config into `prg-contracts`.
- `planner-workload-analyzer`, `heater-batch-selection`, and `prg-contracts` still live in placeholder `Documents\New project*` folders even though their GitHub repos are established.
- Existing `prg-contracts` is contract-only at `C:\Users\JohnKim\Documents\New project 3`; changing that mapping requires John review because the requested `PRG` folder is not a Git repo and is not contract-only.

## Next Best Action

John should review this local folder mapping audit PR, then approve one separate cleanup task:

- clone `planner-workload-analyzer` into the canonical folder first, or
- audit/split `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` into contract and app/orchestrator ownership.
