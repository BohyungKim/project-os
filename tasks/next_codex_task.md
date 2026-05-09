# Next Codex Task

## Objective

Prepare a PRG split plan before changing the `prg-contracts` local working-folder mapping.

## Scope

- Use `project-os` as the central registry.
- Inspect `C:\Users\JohnKim\Desktop\Bins\Projects\PRG`.
- Identify exactly which files are contract/schema material.
- Identify exactly which files are app/orchestrator/dashboard logic.
- Recommend whether contract material should be copied into `BohyungKim/prg-contracts` through a reviewed PR.
- Recommend the separate repo name/path for PRG app/orchestrator/dashboard logic if John wants it under source control.
- Preserve the current verified `prg-contracts` folder until John approves a split:
  - `C:\Users\JohnKim\Documents\New project 3`

## Out Of Scope

- Moving, renaming, deleting, or creating project folders.
- Reading `.env` contents.
- Changing application logic.
- Pushing PRG app code.
- Replacing the existing contract-only `prg-contracts` repo mapping without John review.
- Merging any PR automatically.

## Files To Inspect

- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG\docs\`
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG\PRG_ClaudeCode_Implementation_Guide.md`
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG\pyproject.toml`
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG\src\prg\`
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG\scripts\`
- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG\tests\`
- `C:\Users\JohnKim\Documents\New project 3\schemas\`
- `C:\Users\JohnKim\Documents\New project 3\docs\`
- `C:\Users\JohnKim\Documents\New project 3\examples\`

## Files To Modify

- None in `PRG` during the split-plan task.
- If John approves a docs-only split PR, modify only contract repo files under `C:\Users\JohnKim\Documents\New project 3`.
- Update `project-os` registry files after the approved split plan or split PR.

## Acceptance Criteria

- PRG split plan lists contract/schema files separately from app/orchestrator/dashboard files.
- No `.env` contents are read or copied.
- No folder is moved, renamed, deleted, or created.
- No application logic is changed.
- `prg-contracts` remains contract-only unless John approves a scoped docs/schema update.
- Planner relocation remains clone-first and is not performed during this task.

## Validation Command

```powershell
git -C "C:\Users\JohnKim\Documents\New project 3" status --short --branch
git -C "C:\Users\JohnKim\Documents\New project 3" remote -v
git -C "C:\Users\JohnKim\Desktop\Bins\Projects\PRG" rev-parse --show-toplevel
Get-ChildItem -LiteralPath "C:\Users\JohnKim\Desktop\Bins\Projects\PRG" -Force
```

Expected validation:

- `prg-contracts` stays clean.
- `PRG` still reports no Git repo unless John explicitly initializes or clones later.
- The report clearly states that the task was an audit/split plan, not an implementation change.

## Report-Back Format

- PRG split recommendation
- contract/schema files
- app/orchestrator/dashboard files
- `.env`/secret handling status, without contents
- whether any file changes were made
- validation commands and results
- project-os PR link if registry files changed
- next recommended action
