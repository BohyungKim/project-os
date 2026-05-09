# Codex Project Map

Updated: 2026-05-09 11:37 -04:00

## Control Tower Layout

```text
BohyungKim/project-os
  central control tower
  project registry
  onboarding status
  shared AGENTS.md template
  status/report/task conventions

BohyungKim/planner-workload-analyzer
  established app repo
  current local folder: C:\Users\JohnKim\Documents\New project
  preferred future local folder: C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer
  GitHub repo status: main established at 7427048

BohyungKim/heater-batch-selection
  established app repo
  current local folder: C:\Users\JohnKim\Documents\New project 2
  GitHub repo status: main established at 6e32db7

BohyungKim/prg-contracts
  established contract/schema repo
  current verified local folder: C:\Users\JohnKim\Documents\New project 3
  requested PRG remap candidate: C:\Users\JohnKim\Desktop\Bins\Projects\PRG
  remap status: blocked until PRG is split, because PRG is mixed app/contracts and has no git repo
```

## Project Relationships

### project-os

Role:
- Central registry and operating layer.
- Does not own application code.
- Tracks which project repo is the source of truth for each initiative.

ChatGPT entry point:
- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `reports/latest_execution_report.md`

### planner-workload-analyzer

Role:
- Real project repo for a read-only Microsoft Planner workload analyzer.

Current status:
- GitHub `main` is established.
- Current local folder is still `C:\Users\JohnKim\Documents\New project`.
- Current branch is `main`.
- Local `HEAD` equals `origin/main` at `7427048`.
- Working tree is clean.
- `.env` exists locally but is ignored.

Future local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`

Cleanup rule:
- Prefer a clean clone from GitHub into the preferred path.
- Do not manually move the current folder until John confirms the clone and any local-only `.env` needs.

### heater-batch-selection

Role:
- Real Python app repo for internal heater batch selection.

Current status:
- GitHub `main` is established.
- Current local folder is `C:\Users\JohnKim\Documents\New project 2`.
- Browser automation must remain manual-review / safe dry-run only unless John explicitly approves a narrower production-safe change.

### prg-contracts

Role:
- Contract-only PRG / Manufacturing Copilot schema repo.
- Owns schemas, field registry, taxonomies, examples, and validator tooling.

Current status:
- GitHub `main` is established.
- Current verified local folder is `C:\Users\JohnKim\Documents\New project 3`.
- Local `HEAD` equals `origin/main` at `3455ead`.

Important correction:
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` was audited as a requested remap candidate.
- It contains contract docs, but also app/orchestrator/dashboard logic, scripts, templates, tests, and a root `.env`.
- It is not a Git repo and has no remote URL.
- Therefore it should not replace the current `prg-contracts` local folder as-is.

### PRG Folder Audit

Role:
- Mixed PRG workspace with contract docs plus Python app/orchestrator/dashboard code.

Action:
- Split before repo assignment.
- Contract/schema material can be proposed for `prg-contracts` through a reviewed PR.
- App/orchestrator/dashboard logic should be mapped to a separate PRG application repo if John wants it under source control.

### project-os legacy sync workspace

Role:
- Historical setup workspace for project-os operating rules.

Action:
- Do not turn this into a separate repo.
- Keep only until John confirms it is safe to archive.

## Required Per-Project Source-Of-Truth Files

Every real project repo should contain:

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
