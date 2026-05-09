# Current State

Updated at: 2026-05-09 11:52 America/Toronto

## Project Case

Case 3 - Codex Continuation Sync.

## Current Phase

Local folder mapping audit preserved on a clean branch; PR pending.

## Confirmed

- `project-os/main` includes PR #6.
- Current `project-os` branch: `codex/local-folder-mapping-audit`.
- `project-os` remote: `https://github.com/BohyungKim/project-os.git`.
- Project-os PR #8 is open:
  - `https://github.com/BohyungKim/project-os/pull/8`
- At the start of this task, the active worktree had no uncommitted changes.
- The useful local folder mapping audit changes were already preserved on `codex/correct-local-folder-mapping`.
- Those changes were carried forward onto a clean branch based on current `origin/main`.
- `planner-workload-analyzer` current local path is `C:\Users\JohnKim\Documents\New project`.
- Preferred canonical planner path is `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`.
- `PRG` folder is not a Git repo and contains mixed app/orchestrator/dashboard logic plus contract docs.
- `PRG` has a root `.env`; contents were not read.
- Existing `prg-contracts` contract-only local path remains `C:\Users\JohnKim\Documents\New project 3`.

## Changed

- Updated project registry/status/map files to clearly mark current local path, preferred canonical local path, relocation status, and archive candidates.
- Recorded that `PRG` should not replace `prg-contracts` as-is.
- Recorded a safe planner cleanup plan using clean clone from GitHub.
- Updated next task to canonicalize `planner-workload-analyzer` folder safely.

## Still Incomplete

- `project-os` PR #8 still needs John/ChatGPT review before merge.
- No folders have been moved, renamed, deleted, or cloned yet.
- PRG split decision has not been made.

## Uncertain

- Whether John wants canonical local folders under `C:\Users\JohnKim\Desktop\Bins\Projects` for every repo.
- What the final repo name should be for PRG app/orchestrator logic if it is split from contract material.

## Validation Evidence

Commands run:

```powershell
git status --short --branch
git fetch origin
git switch main
git pull --ff-only origin main
git switch -c codex/local-folder-mapping-audit
git -C "C:\Users\JohnKim\Documents\New project" rev-list --left-right --count origin/main...HEAD
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\PRG" rev-parse --show-toplevel
Get-Content state/project_registry.json | ConvertFrom-Json
git diff --check
```

Results:
- Initial active worktree had no uncommitted changes.
- Planner ahead/behind result was `0/0`.
- `PRG` git check confirmed it is not a Git repo.
- `state/project_registry.json` parsed successfully.
- `git diff --check` passed.

## Current Risk

Low for documentation-only registry changes. Main risk is accidentally treating `PRG` as `prg-contracts` without splitting it, because `PRG` contains app logic and `.env`.
