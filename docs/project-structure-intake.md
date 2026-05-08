# Project Structure Intake

Date: 2026-05-08

Purpose: capture the actual local project structures that Codex can inspect so ChatGPT and Codex can share a clearer source-of-truth view before GitHub publishing.

## Summary

| Local folder | Inferred project | Current phase | Structure status | Validation |
| --- | --- | --- | --- | --- |
| `C:\Users\JohnKim\Documents\New project` | Microsoft Planner Workload Analyzer MVP | Existing project intake | Python package with CLI, config, tests, and report outputs | `python -m pytest` passed: 7 tests |
| `C:\Users\JohnKim\Documents\New project 2` | Unknown | Empty placeholder or abandoned init | No visible project files outside `.git` | Not testable |
| `C:\Users\JohnKim\Documents\New project 3` | PRG Supply Readiness Checker | Architecture planning / MVP definition | Docs-first repo with README and system plan | No tests/code yet |
| `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | project-os operating rules PR workspace | Codex continuation sync | Operating docs/state/report/task repo connected to GitHub | Git branch and remote verified |

## 1. Microsoft Planner Workload Analyzer MVP

Path: `C:\Users\JohnKim\Documents\New project`

### Confirmed Purpose

The README describes this as a read-only Python MVP for extracting Microsoft Planner basic plan data through Microsoft Graph v1.0, normalizing it locally, and reporting workload by assignee.

### Entry Points

- Console script: `planner-workload`
- Python module entry: `python -m planner_analyzer`
- CLI implementation: `src/planner_analyzer/cli.py`

### Important Files And Folders

- `README.md`: setup, run commands, output contract, workload scoring explanation.
- `pyproject.toml`: package metadata, dependencies, test settings, console script.
- `.gitignore`: excludes `.env`, caches, generated `data/`, generated `reports/`, and virtual environments.
- `.env.example`: auth/config template.
- `config/planner_sources.yaml`: plan source list with placeholder plan ID.
- `src/planner_analyzer/`: application package.
- `tests/`: unit tests for config parsing, normalization, and workload analysis.

### Main Modules

- `auth.py`: Microsoft Graph delegated auth through MSAL.
- `graph.py`: small read-only Graph client with retry/pagination helpers.
- `collector.py`: reads plans, buckets, details, tasks, task details, and assignee users.
- `config.py`: loads `.env` settings and Planner source YAML.
- `normalize.py`: converts Graph snapshot payloads into `NormalizedTask` records and workload signals.
- `analysis.py`: builds Pandas dataframes and portfolio/assignee workload summaries.
- `reports.py`: writes JSON/CSV/Markdown outputs and prints a Rich table.
- `models.py`: normalized task data model.
- `cli.py`: command parser and run/report orchestration.

### Data Flow

1. `.env` and `config/planner_sources.yaml` define tenant/client/scopes and enabled Planner plans.
2. `GraphAuthenticator` obtains a delegated Graph access token.
3. `GraphClient` performs read-only GET requests against Microsoft Graph.
4. `PlannerCollector` gathers a raw snapshot for plans, buckets, plan details, tasks, task details, and users.
5. `normalize_snapshot` creates normalized task records.
6. `reports.py` writes:
   - `data/raw/planner_snapshot_YYYYMMDD_HHMMSS.json`
   - `data/normalized/tasks.json`
   - `data/normalized/tasks.csv`
   - `reports/assignee_workload.csv`
   - `reports/workload_report.md`

### Risk Areas

- `.env` exists locally and must not be committed.
- Planner plan IDs may be sensitive if shared broadly.
- Graph permissions include `Tasks.Read`, `Group.Read.All`, and `User.Read`; John should confirm these are acceptable.
- Generated `data/` and `reports/` can contain business data and should remain ignored unless intentionally sanitized.
- Task descriptions are redacted by default unless `STORE_TASK_DESCRIPTIONS` is enabled.
- Repo has no commit yet, no GitHub remote, and is still on `master`.

### Validation

Command run:

```powershell
python -m pytest
```

Result:

```text
7 passed
```

### Recommended Next Step

Treat this as the first candidate repo to publish because it already has code, tests, README, and a clear `.gitignore`.

Safe publish sequence:

1. Add project root `AGENTS.md` from `templates/AGENTS.project.md`.
2. Confirm `.env` is ignored and not staged.
3. Rename branch to `main`.
4. Commit code and docs.
5. Create a private GitHub repo, likely with a name such as `planner-workload-analyzer`.
6. Push `main`.

## 2. Unknown Empty Git Folder

Path: `C:\Users\JohnKim\Documents\New project 2`

### Confirmed Structure

No visible project files were found outside `.git`.

### Current State

- Git repository exists.
- Branch is `master`.
- No commits yet.
- No remote configured.

### Risk Areas

- This may be an accidental or abandoned initialized folder.
- It should not be published until John confirms its purpose.

### Recommended Next Step

John should either identify the intended project for this folder or archive/delete it outside Codex after confirming it is not needed.

## 3. PRG Supply Readiness Checker

Path: `C:\Users\JohnKim\Documents\New project 3`

### Confirmed Purpose

The README defines this as the Supply Readiness Checker, a lower-level engine under PRG / Pre-Release Gate. It answers whether materials required by the Job BOM are ready from inventory, PO, receipt, BTO, and long-lead perspectives.

### Current Phase

Architecture planning / MVP definition.

### Important Files

- `README.md`: product positioning and current phase.
- `docs/SUPPLY_READINESS_CHECKER_SYSTEM_PLAN.md`: full system plan.

### Planned System Shape

The system plan defines:

- Product role under PRG.
- Relationship to Job BOM Comparator.
- Core readiness question.
- System boundary and safety exclusions.
- Readiness levels: OK, Warning, Risk, Blocked / Needs Review, Not Enough Evidence.
- Input domains:
  - job release context
  - material demand
  - inventory snapshot
  - PO / requisition coverage
  - receipt / inspection status
  - BTO / long-lead master
- Rule engine v0.1:
  - inventory coverage
  - PO coverage
  - receipt readiness
  - BTO / long-lead risk
  - data confidence
- Finding types.
- PRG output contract v0.1.
- Suggested owners.
- MVP execution phases.
- Safety policy.
- open questions for John.
- next Codex task.

### Risk Areas

- No implementation code yet.
- No tests yet.
- No root `AGENTS.md` yet.
- No commits yet.
- No remote configured.
- Branch is still `master`.

### Recommended Next Step

This should be published as a docs-first planning repo only after adding `AGENTS.md` and making a first `main` commit. The first implementation task should be contract and sample data, not Epicor writes or automation.

## 4. project-os Operating Rules Workspace

Path: `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working`

### Confirmed Purpose

This folder is a Codex continuation workspace for project operating rules and state continuity. It contains no application product code.

### Important Files

- `AGENTS.md`: consolidated operating rules.
- `state/current_state.md`: verified project state.
- `state/current_state.json`: machine-readable project state.
- `reports/latest_execution_report.md`: latest execution report.
- `tasks/next_codex_task.md`: next task definition.
- `decisions/decision_log.md`: decision history.

### GitHub State

- Branch: `docs/agents-guidelines-sync-mainbase`
- Remote: `https://github.com/BohyungKim/project-os.git`
- Latest verified local commit: `2c940d6 docs(state): record pull request and notion update`
- Remote branch exists and tracks `origin/docs/agents-guidelines-sync-mainbase`.

### Current State

The local state file says PR #1 exists and is mergeable, but John should still confirm the inferred remote and Notion target before merge.

### Recommended Next Step

Review PR #1 for `BohyungKim/project-os`, then merge only if John confirms this is the correct long-term operating repo.

## Practical Conclusion

There is real structure in the local folders:

- `New project` is the strongest first GitHub candidate because it has runnable code and passing tests.
- `New project 3` is a strong docs-first planning repo candidate.
- `agents-md-role-you-are-working` is already a GitHub-connected operations repo workspace.
- `New project 2` currently has no visible project structure.

The next useful action is to map these folder names to final GitHub repo names before publishing.
