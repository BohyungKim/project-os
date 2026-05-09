# Current State

Updated at: 2026-05-09 12:30 America/Toronto

## Project Case

Case 3 - Codex Continuation Sync.

## Current Phase

Job BOM Comparator source-of-truth onboarding prepared locally; GitHub repo creation is the current blocker.

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
- The target GitHub repo does not exist yet from local git credentials.
- `.env` exists locally, was not read, and is not tracked.
- Tracked secret-like filename scan found only `.env.example`.
- Local tests pass: 87 passed.

## Changed

- Prepared `Job BOM Comparator Agent` local source-of-truth onboarding files.
- Committed the onboarding setup locally in the app repo.
- Updated project-os registry and status files to record that the repo is ready for GitHub creation/push.
- Opened project-os PR #9 for John review.

## Still Incomplete

- `planner-workload-analyzer` canonical clone is still missing.
- `heater-batch-selection` canonical clone is still missing.
- `Job BOM Comparator Agent` has not been pushed to GitHub because `BohyungKim/job-bom-comparator` does not exist yet.
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
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-remote https://github.com/BohyungKim/job-bom-comparator.git
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent" ls-files
.\.venv\Scripts\python.exe -B -m pytest
```

Results:
- `prg-contracts` canonical clone is clean on `main...origin/main`.
- `Job BOM Comparator Agent` source-of-truth onboarding commit exists locally.
- `Job BOM Comparator Agent` has no remote because the target GitHub repo does not exist yet.
- `Job BOM Comparator Agent` test result: 87 passed.
- `Project-OS` canonical folder is dirty/old and needs review.

## Current Risk

Medium. The app repo is locally prepared, but GitHub source of truth is not established until John creates `BohyungKim/job-bom-comparator` and Codex pushes the prepared branch/main.
