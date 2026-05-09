# Current State

Updated at: 2026-05-09 12:12 America/Toronto

## Project Case

Case 3 - Codex Continuation Sync.

## Current Phase

Canonical project root correction in progress on PR #8.

## Confirmed

- The canonical local project root is:
  - `C:\Users\JohnKim\Desktop\Bins\Projects`
- `Documents\New project*` paths are non-canonical legacy paths.
- `Documents\Codex\...` paths are Codex execution workspaces, not the default project directory.
- `prg-contracts` canonical clone now exists at:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts`
- `Job BOM Comparator Agent` exists at:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`
- `Job BOM Comparator Agent` is a local git repo but has no remote.
- `Job BOM Comparator Agent` has many modified/untracked files and a local `.env`.
- `Project-OS` canonical folder exists at:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS`
- `Project-OS` canonical folder has a GitHub remote but is dirty/old and needs sync review.

## Changed

- Updated project registry and map to use `C:\Users\JohnKim\Desktop\Bins\Projects` as canonical root.
- Updated `scripts/update-project-status.ps1` default scan paths to inspect canonical project folders.
- Created canonical `prg-contracts` clone.
- Updated latest report and next task to focus on `Job BOM Comparator Agent` onboarding.

## Still Incomplete

- `planner-workload-analyzer` canonical clone is still missing.
- `heater-batch-selection` canonical clone is still missing.
- `Job BOM Comparator Agent` has not been onboarded to GitHub.
- Canonical `Project-OS` folder has not been reconciled with current GitHub main work.

## Uncertain

- Whether John wants canonical folder names to preserve current friendly names, such as `Job BOM Comparator Agent`, or use repo slugs such as `job-bom-comparator`.
- Whether `Project-OS` canonical folder should be repaired in place or replaced by a clean clone after review.

## Validation Evidence

Commands run:

```powershell
git clone https://github.com/BohyungKim/prg-contracts.git "C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts"
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS" status --short --branch
powershell -ExecutionPolicy Bypass -File scripts/update-project-status.ps1
```

Results:
- `prg-contracts` canonical clone is clean on `main...origin/main`.
- `Job BOM Comparator Agent` is dirty and has no remote.
- `Project-OS` canonical folder is dirty/old and needs review.

## Current Risk

Medium until the canonical path cleanup is complete. The main risk is Codex accidentally reading/writing `Documents\New project*` instead of `C:\Users\JohnKim\Desktop\Bins\Projects`.
