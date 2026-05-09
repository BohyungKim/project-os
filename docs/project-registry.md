# Project Registry

Updated: 2026-05-09 16:50 -04:00

Canonical project root:

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

This is the only folder tree that should be treated as John's real active project directory. Any `Documents\New project*` or `Documents\Codex\...` path is a temporary/legacy execution workspace unless John explicitly promotes it.

## Control Tower Rule

`project-os` is the central registry and operating layer. Actual project work should be mapped under:

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

Every real project repo should eventually contain:

- `AGENTS.md`
- `README.md`
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

## Detected Projects In Canonical Root

| Project | Canonical Local Path | Git | GitHub Remote | Source-Of-Truth Status | Working State | Next Action |
| --- | --- | --- | --- | --- | --- | --- |
| project-os | `C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS` | Yes, branch `main` | `https://github.com/BohyungKim/project-os.git` | GitHub repo exists, but this local clone is dirty/old and needs sync review | Modified/untracked files present | Do not use as clean working copy until audited |
| prg-contracts | `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts` | Yes, branch `main` | `https://github.com/BohyungKim/prg-contracts.git` | Established; canonical clone created | Clean, `main...origin/main`, latest `3455ead` | Use this path going forward |
| Job BOM Comparator Agent | `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent` | Yes, branch `codex/source-of-truth-onboarding` | `https://github.com/BohyungKim/job-bom-comparator.git` | Established on `main`; app/product changes are isolated in PR #1 | `main` at `ba2ea94`; PR branch at `f619f49`; tests pass; `.env` exists but is not tracked | Review PR #1 and switch GitHub default branch to `main` if available |
| BOM_Release_Console | `C:\Users\JohnKim\Desktop\Bins\Projects\BOM_Release_Console` | Yes, branch `master` | None | Local project only; GitHub source of truth not established | Modified/untracked files present | Audit before onboarding |
| PRG | `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` | No | None | Not established; mixed app/contracts workspace | `.env`, app/orchestrator/dashboard code, docs, tests | Split before repo assignment |
| planner-workload-analyzer | `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer` | Missing path | `https://github.com/BohyungKim/planner-workload-analyzer.git` | GitHub source of truth established, but canonical local clone missing | Missing canonical clone | Clone here before future local work |
| heater-batch-selection | `C:\Users\JohnKim\Desktop\Bins\Projects\heater-batch-selection` | Missing path | `https://github.com/BohyungKim/heater-batch-selection.git` | GitHub source of truth established, but canonical local clone missing | Missing canonical clone | Clone here before future local work |
| BOM Ordering Automation | `C:\Users\JohnKim\Desktop\Bins\Projects\BOM Ordering Automation` | No | None | Not established | Local folder exists | Audit/classify |
| Job Closing Bottleneck Agent | `C:\Users\JohnKim\Desktop\Bins\Projects\Job Closing Bottleneck Agent` | No | None | Not established | Local folder exists | Audit/classify |
| Neptronic Selection Automation | `C:\Users\JohnKim\Desktop\Bins\Projects\Neptronic Selection Automation` | No | None | Not established | Local folder exists | Audit/classify |
| Part Transaction Pattern Error Analysis | `C:\Users\JohnKim\Desktop\Bins\Projects\Part Transaction Pattern Error Analysis` | No | None | Not established | Local folder exists | Audit/classify |
| PO Release Engineering Workflow | `C:\Users\JohnKim\Desktop\Bins\Projects\PO Release Engineering Workflow` | No | None | Not established | Local folder exists | Audit/classify |
| Real Time Issuance | `C:\Users\JohnKim\Desktop\Bins\Projects\Real Time Issuance` | No | None | Not established | Local folder exists | Audit/classify |

## Important Correction

Previous registry entries used paths such as:

- `C:\Users\JohnKim\Documents\New project`
- `C:\Users\JohnKim\Documents\New project 2`
- `C:\Users\JohnKim\Documents\New project 3`
- `C:\Users\JohnKim\Documents\Codex\...`

These should not be treated as the default project directory. The canonical project directory is:

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

## prg-contracts Local Clone

Canonical clone:

```text
C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts
```

Status:

- Branch: `main`
- Remote: `https://github.com/BohyungKim/prg-contracts.git`
- Latest commit: `3455ead docs: mark prg contracts source of truth established`
- Working tree: clean

Legacy/non-canonical clone:

```text
C:\Users\JohnKim\Documents\New project 3
```

Keep it untouched for now, but do not use it as the default project path going forward.

## Job BOM Comparator Local Repo

Current local repo:

```text
C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent
```

Status:

- Branch: `codex/source-of-truth-onboarding`
- Remote: `https://github.com/BohyungKim/job-bom-comparator.git`
- Origin remote: `https://github.com/BohyungKim/job-bom-comparator.git`
- Pushed branch: `codex/source-of-truth-onboarding`
- Remote HEAD branch: `codex/source-of-truth-onboarding`
- Stable main commit: `ba2ea94 docs: establish job bom main baseline status`
- Feature PR: `https://github.com/BohyungKim/job-bom-comparator/pull/1`
- Feature branch commit: `f619f49 docs: link job bom feature review PR`
- Initial onboarding commit: `42f2ee7 docs: prepare source-of-truth onboarding`
- Previous app baseline commit: `b520f4a Surface sibling and owner signals`
- Validation: dirty local tree `.\.venv\Scripts\python.exe -B -m pytest` -> 87 passed; clean pushed baseline worktree -> 48 passed
- `.env` exists locally and was not read
- `.env` is not tracked
- Tracked secret-like filename scan only found `.env.example`
- Existing app/product changes remain modified or untracked and were preserved

Stable `main` exists at `ba2ea94`. The app/product changes are isolated in PR #1 from `codex/source-of-truth-onboarding` to `main`; this PR must be reviewed before merge. GitHub default branch still reports `codex/source-of-truth-onboarding`, so John may need to switch the default branch to `main` in GitHub settings.

## Cleanup Plan

1. Use `C:\Users\JohnKim\Desktop\Bins\Projects` as the only canonical local project root.
2. Keep `Documents\New project*` folders as legacy/non-canonical until each has a canonical clone or migration plan.
3. Clone missing established repos into canonical paths:
   - `planner-workload-analyzer`
   - `heater-batch-selection`
4. Review `job-bom-comparator` PR #1 before merge and switch the default branch to `main` if needed.
5. Audit/split `PRG` before assigning it to `prg-contracts` or a PRG app repo.
