# Codex Project Map

Updated: 2026-05-09 11:35 -04:00

## Control Tower Layout

```text
BohyungKim/project-os
  central control tower
  project registry
  onboarding status
  shared AGENTS.md template
  status/report/task conventions

BohyungKim/planner-workload-analyzer
  real app repo
  current local folder: C:\Users\JohnKim\Documents\New project
  GitHub main status: established

BohyungKim/heater-batch-selection
  real app repo
  current local folder: C:\Users\JohnKim\Documents\New project 2
  GitHub main status: established
  safety note: browser automation stays dry-run/manual-review unless John explicitly approves otherwise

BohyungKim/prg-contracts
  shared PRG / Manufacturing Copilot contract repo
  current local folder: C:\Users\JohnKim\Documents\New project 3
  GitHub main status: established
  defines PRGCase-compatible contract output for feeder modules
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
- Read-only Microsoft Planner workload analyzer.
- First real app repo onboarded into GitHub source-of-truth flow.

Current status:
- GitHub `main` is established.
- Tests passed during onboarding: 7 passed.

Repo:
- `BohyungKim/planner-workload-analyzer`

### heater-batch-selection

Role:
- Internal heater batch selection MVP.
- Second real app repo onboarded into GitHub source-of-truth flow.

Current status:
- GitHub `main` is established.
- Tests passed during onboarding: 9 passed.
- Browser automation safety rules are documented.

Repo:
- `BohyungKim/heater-batch-selection`

### prg-contracts

Role:
- Shared PRG / Manufacturing Copilot contract source of truth.
- Defines the common output contract that feeder modules should emit.

Current status:
- GitHub `main` is established.
- Latest known remote main commit: `3455eaddc9413acf12f195cd58ad04deaef9a4d0`.
- Validation command passed:
  - `python tools/validate_prg_case.py examples/*.json`

Repo:
- `BohyungKim/prg-contracts`

Contains:
- `schemas/prg_case.schema.json`
- `schemas/evidence_item.schema.json`
- `schemas/action_item.schema.json`
- `docs/field_registry.md`
- `docs/severity_taxonomy.md`
- `docs/readiness_area_taxonomy.md`
- `docs/owner_mapping.md`
- `docs/schema_change_request_process.md`
- `docs/codex_prompt_guardrails.md`
- `examples/*_prg_case_sample.json`
- `tools/validate_prg_case.py`

Guardrail:
- This is not a dashboard repo.
- This is not the POBTO checker repo.
- This is not an Epicor write-back repo.
- This is not a production automation repo.
- This is not where feeder-specific detection logic belongs.

### project-os legacy sync workspace

Role:
- Historical setup workspace for project-os operating rules.

Action:
- Do not turn this into a separate repo.
- Keep only until John confirms it is safe to archive.

## First PRG Contract Integration Candidate

Recommended next repo:
- `job-bom-comparator`

Reason:
- Comparator output is a natural first feeder for PRGCase.
- `prg-contracts` already includes `examples/comparator_prg_case_sample.json`.

Expected pattern:
- Feeder repo owns detection logic.
- Feeder repo emits PRGCase-compatible output.
- `prg-contracts` owns shared schema and taxonomy.
- `project-os` tracks overall status.

## How John Should Ask ChatGPT Later

```text
Use project-os as the central registry.
Then use prg-contracts current_state.md as the PRG contract source of truth.
Tell me which feeder repo should integrate next and what files ChatGPT should review.
```

## Required Per-Project Source-Of-Truth Files

Every real project repo should contain:

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`
