# Next Codex Task

## Objective

Integrate the first feeder repo with `prg-contracts` PRGCase-compatible output.

Recommended first feeder:
- `job-bom-comparator`

## Scope

- Use `project-os/main` as the central registry after this PR is merged.
- Use `prg-contracts/main` as the PRG / Manufacturing Copilot contract source of truth.
- Locate or onboard the `job-bom-comparator` repo.
- Inspect its existing output/report shape.
- Add the smallest safe PRGCase-compatible export or report output.
- Validate generated/sample output against `prg-contracts/tools/validate_prg_case.py` or equivalent copied validation command.
- Update the feeder repo state/report/task files.
- Update `project-os` registry if project status changes.

## Out Of Scope

- Changing `prg-contracts` unless a schema change request is required.
- Inventing incompatible PRGCase fields.
- Adding Epicor write-back logic.
- Adding production-impacting automation.
- Merging any PR automatically.

## Files To Inspect

- `project-os/state/project_registry.json`
- `project-os/docs/project-registry.md`
- `prg-contracts/schemas/prg_case.schema.json`
- `prg-contracts/docs/field_registry.md`
- `prg-contracts/examples/comparator_prg_case_sample.json`
- `job-bom-comparator` README/source/output files once the repo path is confirmed

## Files To Modify

In the feeder repo, expected:
- source/output module that owns report/export generation
- tests or sample fixture files for PRGCase-compatible output
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md` if a decision is made

In `project-os`, if status changes:
- `docs/project-registry.md`
- `state/project_registry.json`
- `docs/repo-onboarding-status.md`
- `docs/realtime-repo-status.md`
- `reports/latest_execution_report.md`

## Acceptance Criteria

- `job-bom-comparator` emits or can export at least one PRGCase-compatible sample.
- Sample output validates against the `prg-contracts` contract.
- No Epicor write-back or production-impacting automation is added.
- Feeder repo source-of-truth status files are updated.
- `project-os` reflects the feeder integration status.
- Work is delivered through branch/PR, not auto-merged.

## Validation Command

```powershell
python tools/validate_prg_case.py examples/*.json
Get-Content state/current_state.json | ConvertFrom-Json
git diff --check
```

Exact feeder validation may change once the `job-bom-comparator` repo structure is inspected.

## Report-Back Format

- feeder repo name
- branch name
- PR link
- PRGCase sample path
- validation command/result
- changed files
- risks
- next recommended feeder or schema change request
