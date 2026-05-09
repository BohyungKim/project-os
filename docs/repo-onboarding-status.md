# Repo Onboarding Status

Updated: 2026-05-09 16:42 -04:00

Canonical project root:

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

## Summary

| Priority | Project | Canonical Local Path | GitHub Status | Local Status | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS` | `BohyungKim/project-os` exists | Canonical clone exists but is dirty/old | Audit/sync before making it active workspace |
| 1 | prg-contracts | `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts` | Established | Clean clone created, `main...origin/main` | Use this path going forward |
| 2 | Job BOM Comparator Agent | `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent` | Prepared branch pushed to `BohyungKim/job-bom-comparator` | Remote HEAD is `codex/source-of-truth-onboarding`; latest pushed commit `c5f7555`; app changes preserved | John reviews stable `main` promotion path |
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
- Remote: none.
- Origin remote: `https://github.com/BohyungKim/job-bom-comparator.git`.
- Pushed branch: `codex/source-of-truth-onboarding`.
- Remote HEAD branch: `codex/source-of-truth-onboarding`.
- Latest pushed commit: `c5f7555 docs: confirm job bom GitHub branch push`.
- Initial onboarding commit: `42f2ee7 docs: prepare source-of-truth onboarding`.
- Previous app baseline commit: `b520f4a Surface sibling and owner signals`.
- `AGENTS.md`, `.gitignore`, and source-of-truth state/report/task/decision files were committed locally.
- `.\.venv\Scripts\python.exe -B -m pytest` passed with 87 tests.
- `.env` exists locally but was not read and is not tracked.
- Tracked secret-like filename scan found only `.env.example`.
- Existing app/product changes remain modified or untracked and were preserved.

Status:
- Prepared source-of-truth branch is pushed to GitHub.
- Stable `main` source of truth is not established yet.

John action required:
- Review whether `codex/source-of-truth-onboarding` should be promoted to `main`.
- Review existing modified/untracked app/product files before deciding the stable baseline scope.

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
Review or promote Job BOM Comparator Agent source-of-truth branch.

Local folder:
C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent

Rules:
- Do not push secrets.
- Do not read .env contents.
- Do not discard local changes.
- Use the existing local branch codex/source-of-truth-onboarding.
- Confirm origin points to https://github.com/BohyungKim/job-bom-comparator.git.
- Decide whether to promote to main or create a separate main base.
- Update project-os after push.
```
