# Codex Project Map

Updated: 2026-05-09 12:30 -04:00

## Canonical Project Root

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

All active project paths should be mapped under this root. `Documents\New project*` and `Documents\Codex\...` paths are non-canonical legacy/execution paths.

## Control Tower Layout

```text
C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS
  canonical local folder for BohyungKim/project-os
  status: exists, git repo, but dirty/old and needs sync review

C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts
  canonical local folder for BohyungKim/prg-contracts
  status: clean clone, main tracks origin/main

C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent
  canonical local folder for job-bom-comparator candidate
  status: local source-of-truth setup prepared, no remote, GitHub repo creation required

C:\Users\JohnKim\Desktop\Bins\Projects\PRG
  canonical PRG workspace
  status: mixed app/contracts folder, not git, .env exists
```

## Active Repo Facts

### project-os

Canonical local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS`

Remote:
- `https://github.com/BohyungKim/project-os.git`

Important:
- The current Codex execution workspace for this PR is still under `Documents\Codex\...`.
- That is not the canonical project directory.
- The canonical `Project-OS` folder exists but is dirty/old and should be audited before becoming the active working copy.

### prg-contracts

Canonical local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts`

Remote:
- `https://github.com/BohyungKim/prg-contracts.git`

Status:
- Branch `main`.
- Latest commit `3455ead`.
- Clean working tree.

### Job BOM Comparator Agent

Canonical local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`

Status:
- Git repo exists.
- Branch `codex/source-of-truth-onboarding`.
- No `origin` remote.
- Target remote `https://github.com/BohyungKim/job-bom-comparator.git` currently does not exist.
- Latest onboarding commit `42f2ee7`.
- Tests pass: 87 passed with local venv pytest.
- Source-of-truth files are committed locally.
- Existing app/product changes remain modified/untracked and were not committed by this onboarding step.
- `.env` exists locally but is not tracked.

This should be treated as the next onboarding candidate. It is prepared locally, but it is not yet a GitHub source-of-truth repo because John still needs to create `BohyungKim/job-bom-comparator`.

### PRG

Canonical local path:
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG`

Status:
- Not a Git repo.
- Mixed app/orchestrator/dashboard and contract docs.
- `.env` exists.

Do not map this directly to `prg-contracts` without a split plan.

## Missing Canonical Clones

These GitHub repos are established, but canonical local clones under `Desktop\Bins\Projects` are currently missing:

- `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`
- `C:\Users\JohnKim\Desktop\Bins\Projects\heater-batch-selection`

Clone them into the canonical root before future local work.

## Archive Candidates

Non-canonical legacy paths that should eventually be retired only after review:

- `C:\Users\JohnKim\Documents\New project`
- `C:\Users\JohnKim\Documents\New project 2`
- `C:\Users\JohnKim\Documents\New project 3`
- `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of`

Do not delete these until John explicitly approves after canonical clones are verified.
