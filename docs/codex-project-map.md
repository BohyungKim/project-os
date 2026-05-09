# Codex Project Map

Updated: 2026-05-09 11:52 -04:00

## Control Tower Layout

```text
BohyungKim/project-os
  central control tower
  current local path: C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of
  preferred canonical path: same as current for now
  relocation status: no relocation needed now

BohyungKim/planner-workload-analyzer
  established app repo
  current local path: C:\Users\JohnKim\Documents\New project
  preferred canonical path: C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer
  relocation status: clone from GitHub later; do not manually move yet

BohyungKim/heater-batch-selection
  established app repo
  current local path: C:\Users\JohnKim\Documents\New project 2
  preferred canonical path: C:\Users\JohnKim\Desktop\Bins\Projects\heater-batch-selection
  relocation status: not audited for relocation yet
  safety note: browser automation stays dry-run/manual-review unless John explicitly approves otherwise

BohyungKim/prg-contracts
  established contract/schema repo
  current verified local path: C:\Users\JohnKim\Documents\New project 3
  preferred canonical path: C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts
  requested PRG remap candidate: C:\Users\JohnKim\Desktop\Bins\Projects\PRG
  remap status: blocked until PRG is split, because PRG is mixed app/contracts and has no git repo

PRG folder audit
  current local path: C:\Users\JohnKim\Desktop\Bins\Projects\PRG
  preferred canonical ownership: split contract material and app/orchestrator material
  relocation status: split decision required before repo assignment
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

Preferred canonical local path:
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

Preferred canonical local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\heater-batch-selection`

Cleanup rule:
- Relocation was not audited in this task.
- Keep the current local folder authoritative until a separate cleanup task verifies clone, tests, and browser safety files.

### prg-contracts

Role:
- Contract-only PRG / Manufacturing Copilot schema repo.
- Owns schemas, field registry, taxonomies, examples, and validator tooling.

Current status:
- GitHub `main` is established.
- Current verified local folder is `C:\Users\JohnKim\Documents\New project 3`.
- Local `HEAD` equals `origin/main` at `3455ead`.

Preferred canonical local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts`

Important correction:
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` was audited as a requested remap candidate.
- It contains contract docs, but also app/orchestrator/dashboard logic, scripts, templates, tests, and a root `.env`.
- It is not a Git repo and has no remote URL.
- Therefore it should not replace the current `prg-contracts` local folder as-is.

### PRG Folder Audit

Role:
- Mixed PRG workspace with contract docs plus Python app/orchestrator/dashboard code.

Current local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG`

Relocation status:
- Split before repo assignment.
- Contract/schema material can be proposed for `prg-contracts` through a reviewed PR.
- App/orchestrator/dashboard logic should be mapped to a separate PRG application repo if John wants it under source control.
- Do not read or push `.env`.

### project-os legacy sync workspace

Role:
- Historical setup workspace for project-os operating rules.

Current local path:
- `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working`

Archive status:
- Archive candidate after John confirms it is no longer needed.
- Do not turn this into a separate repo.

## Archive Candidates

- `C:\Users\JohnKim\Documents\New project`: archive candidate only after planner canonical clone is verified and `.env` needs are handled.
- `C:\Users\JohnKim\Documents\New project 2`: future archive candidate only after heater canonical clone and browser safety review.
- `C:\Users\JohnKim\Documents\New project 3`: future archive candidate only after `prg-contracts` canonical clone and PRG split review.
- `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working`: archive candidate after John confirms the legacy sync workspace is no longer needed.

## Required Per-Project Source-Of-Truth Files

Every real project repo should contain:

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
