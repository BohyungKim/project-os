# Repo Onboarding Status

Updated: 2026-05-09 12:12 -04:00

Canonical project root:

```text
C:\Users\JohnKim\Desktop\Bins\Projects
```

## Summary

| Priority | Project | Canonical Local Path | GitHub Status | Local Status | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `C:\Users\JohnKim\Desktop\Bins\Projects\Project-OS` | `BohyungKim/project-os` exists | Canonical clone exists but is dirty/old | Audit/sync before making it active workspace |
| 1 | prg-contracts | `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts` | Established | Clean clone created, `main...origin/main` | Use this path going forward |
| 2 | Job BOM Comparator Agent | `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent` | No remote yet | Local git repo, dirty, `.env` exists | Secrets/working-tree audit before onboarding |
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
- Branch: `master`.
- Remote: none.
- Latest commit: `b520f4a Surface sibling and owner signals`.
- Working tree has many modified/untracked files.
- `.env` exists.

Status:
- Not a GitHub source-of-truth repo yet.
- Do not push until secrets and working-tree scope are audited.

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
Audit and prepare Job BOM Comparator Agent for GitHub source-of-truth onboarding.

Local folder:
C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent

Rules:
- Do not push secrets.
- Do not read .env contents.
- Do not discard local changes.
- Do not add a remote until the working tree and .gitignore are audited.
- Report which files are modified/untracked and which should be included in the first onboarding commit.
```
