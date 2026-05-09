# Repo Onboarding Status

Updated: 2026-05-09 16:50 -04:00

Canonical project root:

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

## Summary

| Priority | Project | Canonical Local Path | GitHub Status | Local Status | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS` | `BohyungKim/project-os` exists | Canonical clone exists but is dirty/old | Audit/sync before making it active workspace |
| 1 | prg-contracts | `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts` | Established | Clean clone created, `main...origin/main` | Use this path going forward |
| 2 | Job BOM Comparator Agent | `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent` | `main` established in `BohyungKim/job-bom-comparator` | `main` at `ba2ea94`; PR #1 branch at `f619f49`; default branch still reports onboarding branch | Review PR #1, then switch default branch to `main` if needed |
| 3 | planner-workload-analyzer | `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer` | Established | Canonical clone missing | Clone here before future work |
| 4 | heater-batch-selection | `C:\Users\JohnKim\Desktop\Bins\Projects\heater-batch-selection` | Established | Canonical clone missing | Clone here before future work |
| 5 | PRG | `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` | No repo yet | Mixed workspace, not git, `.env` exists | Split plan before repo assignment |

## Correction

The correct project directory is:

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

Do not default future project mappings to:

- `C:\Users\JohnKim\Documents\New project`
- `C:\Users\JohnKim\Documents\New project 2`
- `C:\Users\JohnKim\Documents\New project 3`
- `C:\Users\JohnKim\Documents\Codex\...`

Those are non-canonical legacy or execution workspaces.

## Job BOM Comparator Status

Current local repo:

```text
C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent
```

Confirmed:

- Git repo exists.
- Branch: `codex/source-of-truth-onboarding`.
- Remote: `https://github.com/BohyungKim/job-bom-comparator.git`.
- Origin remote: `https://github.com/BohyungKim/job-bom-comparator.git`.
- Pushed branch: `codex/source-of-truth-onboarding`.
- Remote HEAD branch: `codex/source-of-truth-onboarding`.
- Stable main commit: `ba2ea94 docs: establish job bom main baseline status`.
- Feature PR: `https://github.com/BohyungKim/job-bom-comparator/pull/1`.
- Feature branch commit: `f619f49 docs: link job bom feature review PR`.
- Initial onboarding commit: `42f2ee7 docs: prepare source-of-truth onboarding`.
- Previous app baseline commit: `b520f4a Surface sibling and owner signals`.
- `AGENTS.md`, `.gitignore`, and source-of-truth state/report/task/decision files were committed locally.
- Dirty local tree `.\.venv\Scripts\python.exe -B -m pytest` passed with 87 tests.
- Clean pushed baseline worktree passed with 48 tests.
- `.env` exists locally but was not read and is not tracked.
- Tracked secret-like filename scan found only `.env.example`.
- Existing app/product changes remain modified or untracked and were preserved.

Status:
- Stable `main` branch exists.
- App/product changes are isolated in PR #1.
- GitHub default branch still reports `codex/source-of-truth-onboarding`.

John action required:
- Switch the GitHub default branch to `main` if the GitHub UI still shows `codex/source-of-truth-onboarding`.
- Review PR #1 before merge.

## prg-contracts Status

Canonical local repo:

```text
C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts
```

Confirmed:

- Git repo exists.
- Branch: `main`.
- Remote: `https://github.com/BohyungKim/prg-contracts.git`.
- Latest commit: `3455ead docs: mark prg contracts source of truth established`.
- Working tree is clean.

Legacy/non-canonical folder:

```text
C:\Users\JohnKim\Documents\New project 3
```

Do not use the legacy folder as the default path going forward.

## Exact Next Prompt

```text
Use project-os main as the central registry.

Canonical project root:
C:\Users\JohnKim\Desktop\Bins\Projects

Task:
Review Job BOM Comparator PR #1 before merge.

Local folder:
C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent

Rules:
- Do not push secrets.
- Do not read .env contents.
- Do not discard local changes.
- Use the existing local branch codex/source-of-truth-onboarding.
- Confirm origin points to https://github.com/BohyungKim/job-bom-comparator.git.
- Confirm main exists and default branch is main.
- Do not include dirty app/product files without explicit scope review.
- Update project-os after push.
```
