# Latest Execution Report

Date: 2026-05-09
Branch: `codex/correct-local-folder-mapping`
Project-os PR: pending

## What Changed

- Audited `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` as the requested `prg-contracts` remap candidate.
- Confirmed `PRG` is not contract-only:
  - contract/schema docs exist,
  - app/orchestrator/dashboard code exists,
  - tests exist,
  - `.env` exists,
  - no `.git` repo or remote URL exists.
- Confirmed the existing contract-only `prg-contracts` repo is still at:
  - `C:\Users\JohnKim\Documents\New project 3`
  - `https://github.com/BohyungKim/prg-contracts.git`
- Confirmed `planner-workload-analyzer` is currently at:
  - `C:\Users\JohnKim\Documents\New project`
  - `https://github.com/BohyungKim/planner-workload-analyzer.git`
- Confirmed planner has no unpushed local changes relative to `origin/main`.
- Recorded the preferred future planner local path:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`
- Updated registry/status/map/report/task/decision files only.

## What Did Not Change

- No application logic was changed.
- No folder was deleted, renamed, moved, or created for app projects.
- No `.env` contents were read.
- No app repo code was pushed.
- No PR was merged automatically.

## Audit Evidence

`PRG` folder:

- Contract/schema docs:
  - `docs\PRG_DATA_CONTRACT.md`
  - `docs\epicor_schema_notes.md`
  - `docs\factors.md`
  - `docs\architecture.md`
  - `docs\decisions\001-factor-plugin-pattern.md`
- App/orchestrator/dashboard evidence:
  - `src\prg\api.py`
  - `src\prg\epicor\client.py`
  - `src\prg\templates\index.html`
  - `scripts\daily_scan.py`
  - `scripts\run_against_job.py`
- Roadmap/process docs:
  - `PRG_ClaudeCode_Implementation_Guide.md`
  - `docs\PRG_CHECKLIST.md`
  - `docs\HUMAN_IN_THE_LOOP_POLICY.md`
- Tests:
  - `tests\unit`
  - `tests\integration`
- Git:
  - `git -C C:\Users\JohnKim\Desktop\Bins\Projects\PRG rev-parse --show-toplevel` failed because it is not a Git repo.
- Secrets/local config:
  - `.env` exists at the root. Contents were not read.

`planner-workload-analyzer` folder:

- Branch: `main`.
- Remote: `https://github.com/BohyungKim/planner-workload-analyzer.git`.
- Local `HEAD`: `7427048`.
- `origin/main`: `7427048`.
- Ahead/behind: `0/0`.
- Working tree: clean.
- `.env` exists but is ignored; `.env.example` is tracked.

## Validation Results

Commands run:

```powershell
git -C "C:\Users\JohnKim\Documents\New project" fetch origin
git -C "C:\Users\JohnKim\Documents\New project" rev-list --left-right --count origin/main...HEAD
git -C "C:\Users\JohnKim\Documents\New project" status --porcelain=v1
git -C "C:\Users\JohnKim\Documents\New project 3" status -sb
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\PRG" rev-parse --show-toplevel
Get-Content state/project_registry.json | ConvertFrom-Json
git diff --check
powershell -ExecutionPolicy Bypass -File scripts/update-project-status.ps1
```

Results:

- Planner ahead/behind result was `0/0`.
- Planner status output was empty, confirming no uncommitted local changes.
- `prg-contracts` status showed `main...origin/main`.
- `PRG` git check confirmed it is not a Git repo.
- `state/project_registry.json` parsed successfully.
- `git diff --check` passed.
- `docs/realtime-repo-status.md` was refreshed.

## Risks

- `PRG` contains `.env` and mixed app logic. Mapping it directly to `prg-contracts` could leak scope and confuse contract-only ownership.
- The current verified `prg-contracts` working folder is still the contract-only repo at `C:\Users\JohnKim\Documents\New project 3`; changing that mapping needs John review.
- Planner cleanup should use clone-from-GitHub first so the placeholder folder can be retired later without losing ignored local configuration.

## What ChatGPT Should Review Next

- Review whether `PRG` should be split into:
  - contract/schema files for `BohyungKim/prg-contracts`, and
  - app/orchestrator/dashboard files for a separate PRG application repo.
- Review the planner clone-based relocation plan before any folder cleanup.
