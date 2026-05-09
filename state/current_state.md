# Current State

Updated at: 2026-05-09 16:50 America/Toronto

## Project Case

Case 3 - Codex Continuation Sync.

## Current Phase

Job BOM Comparator `main` baseline established; GitHub default branch still needs review.

## Confirmed

- The canonical local project root is:
  - `C:\Users\JohnKim\Desktop\Bins\Projects`
- `Documents\New project*` paths are non-canonical legacy paths.
- `Documents\Codex\...` paths are Codex execution workspaces, not the default project directory.
- `prg-contracts` canonical clone now exists at:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts`
- `Job BOM Comparator Agent` exists at:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`
- `Job BOM Comparator Agent` is a local git repo with GitHub remote configured.
- `Job BOM Comparator Agent` has many modified/untracked files and a local `.env`.
- `Project-OS` canonical folder exists at:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS`
- `Project-OS` canonical folder has a GitHub remote but is dirty/old and needs sync review.
- project-os PR #8 has been merged into `main`.
- `Job BOM Comparator Agent` canonical local folder is:
  - `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`
- project-os PR #9 is open for this registry update:
  - `https://github.com/BohyungKim/project-os/pull/9`
- `Job BOM Comparator Agent` is on branch `codex/source-of-truth-onboarding`.
- Local onboarding commit exists:
  - `42f2ee7 docs: prepare source-of-truth onboarding`
- Target GitHub remote checked:
  - `https://github.com/BohyungKim/job-bom-comparator.git`
- Origin is configured and the prepared branch has been pushed.
- Remote HEAD branch is `codex/source-of-truth-onboarding`.
- Latest remote commit is `ba2ea947f04d56bc8ca5f9a8ffe9879d8ec6234c`.
- Stable `main` exists and points to the same commit as `codex/source-of-truth-onboarding`.
- GitHub default branch still reports as `codex/source-of-truth-onboarding`.
- `.env` exists locally, was not read, and is not tracked.
- Tracked secret-like filename scan found only `.env.example`.
- Local tests pass: 87 passed.

## Changed

- Prepared `Job BOM Comparator Agent` local source-of-truth onboarding files.
- Committed the onboarding setup locally in the app repo.
- Updated project-os registry and status files to record that `main` exists.
- Opened project-os PR #9 for John review.

## Still Incomplete

- `planner-workload-analyzer` canonical clone is still missing.
- `heater-batch-selection` canonical clone is still missing.
- GitHub default branch may still need to be switched to `main`.
- Canonical `Project-OS` folder has not been reconciled with current GitHub main work.

## Uncertain

- Whether John wants to keep the canonical folder name as `Job BOM Comparator Agent` after the GitHub repo becomes `job-bom-comparator`.
- Whether `Project-OS` canonical folder should be repaired in place or replaced by a clean clone after review.

## Validation Evidence

Commands run:

```powershell
git clone https://github.com/BohyungKim/prg-contracts.git "C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts"
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" status --short --branch
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS" status --short --branch
powershell -ExecutionPolicy Bypass -File scripts/update-project-status.ps1
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" push -u origin codex/source-of-truth-onboarding
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-remote --heads origin
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" push origin HEAD:refs/heads/main
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-files
.\.venv\Scripts\python.exe -B -m pytest
```

Results:
- `prg-contracts` canonical clone is clean on `main...origin/main`.
- `Job BOM Comparator Agent` `main` and `codex/source-of-truth-onboarding` both point to `ba2ea947f04d56bc8ca5f9a8ffe9879d8ec6234c`.
- `Job BOM Comparator Agent` test result: 87 passed.
- `Project-OS` canonical folder is dirty/old and needs review.

## Current Risk

Medium-low. Stable `main` exists, but GitHub default branch still reports `codex/source-of-truth-onboarding`; future work should explicitly target `main` until default branch is switched.
