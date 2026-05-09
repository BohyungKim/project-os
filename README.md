# project-os

GitHub, Codex, and ChatGPT source-of-truth setup.

This repository is the operating hub for John's beginner-friendly setup where each project uses GitHub as the shared source of truth.

## Project Purpose

This repo is not an application runtime. It is the source-of-truth setup and status hub that helps John, ChatGPT, and Codex stay aligned across project work.

It records:

- how GitHub should be used as the stable reference point
- which local project folders have been discovered
- what each project appears to contain
- what is confirmed, incomplete, or risky
- what Codex should do next
- what John must review before publishing or merging

## PRG 안에서의 역할

`project-os` is the PRG operating control tower. It tracks which PRG repos exist, which branch is the stable source of truth, what each repo is responsible for, what Codex should do next, and what John must review before a repo is treated as operationally safe.

This repo should not contain PRG module runtime code, Epicor/Planner/NepConnect automation, or production-impacting business logic. Those belong in their own project repos and should be summarized here only as source-of-truth status.

## Final Structure

```text
GitHub Repo = Source of Truth
main = stable baseline
feature branch = Codex work area
PR = ChatGPT/Codex review area
AGENTS.md = repo-wide operating rules
Codex Skills = repeatable development manuals
```

## Why This Exists

John needs two things:

1. ChatGPT should be able to understand a project's current state quickly from the repo.
2. Every time Codex updates a project, the repo should also receive a real-time status update so the current source of truth stays fresh.

## Beginner Workflow

### 1. Create a GitHub repo

- Use lowercase and hyphenated names.
- Use private repos for company or internal code.
- Prefer one repo per project at the beginning.

Example repo names:

- `bom-console`
- `epicor-chatbot`
- `job-bom-comparator`
- `transaction-analysis-system`
- `john-executive-assistant-v1`

### 2. Connect a local project folder

For a new local project:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin <GitHub repo URL>
git push -u origin main
```

For a folder that already has git:

```bash
git remote -v
git status
git branch
```

### 3. Add repo operating rules

Every project repo should have an `AGENTS.md` at the repo root. Use this repo's `templates/AGENTS.project.md` as the starter.

### 4. Ask Codex for intake before code changes

```text
Read this repository and explain the architecture for a beginner maintainer.
Do not modify code.
Identify:
1. main entry points
2. important folders
3. data flow
4. risky areas
5. what AGENTS.md rules should be added
```

### 5. Keep Codex work off main

```text
Create or use a feature branch.
Do not modify unrelated files.
First explain the plan.
Then make the smallest safe change.
Open a PR or provide a diff for review.
```

### 6. Ask ChatGPT using a clear reference point

Main branch question:

```text
Use the current main branch as the stable source of truth.
Explain the current project structure and recommend the next 3 improvements.
```

PR or diff question:

```text
Use this PR/diff as the live work context.
Compare it against main and explain:
1. what changed
2. what could break
3. what tests I should run
4. whether it is safe to merge
```

## Daily Operating Routine

Morning:
- Confirm current structure and today's priority from `main`.

During development:
- Codex works on a feature branch.
- Keep commits small.
- Push branch and open a PR when review is needed.

After work:
- Refresh repo status docs.
- Create or update PR.
- Ask ChatGPT for PR/diff review.
- Merge only when safe.

Night:
- No automatic source code edits at first.
- Generate reports or draft docs only.

## How To Run

Refresh the generated repo status snapshot:

```powershell
powershell -ExecutionPolicy Bypass -File scripts/update-project-status.ps1
```

Review the current source-of-truth files:

```powershell
Get-Content state/current_state.md
Get-Content reports/latest_execution_report.md
Get-Content tasks/next_codex_task.md
```

## How To Test

This repo currently has no application test suite. Use these checks for the source-of-truth setup:

```powershell
git status --short --branch
git diff --check
powershell -ExecutionPolicy Bypass -File scripts/update-project-status.ps1
Get-Content state/current_state.json | ConvertFrom-Json
```

For discovered project folders, run their project-specific tests. For example:

```powershell
python -m pytest
```

## Status Files

- `state/current_state.md`: human-readable current project state.
- `state/current_state.json`: machine-readable current project state.
- `reports/latest_execution_report.md`: latest Codex execution report.
- `tasks/next_codex_task.md`: next recommended Codex task.
- `decisions/decision_log.md`: decisions that affect future work.
- `docs/today-checklist-status.md`: today's setup checklist and evidence.
- `docs/project-registry.md`: discovered local project folders and Git/GitHub state.
- `docs/project-structure-intake.md`: actual structure summaries for discovered local project folders.
- `docs/realtime-repo-status.md`: generated status snapshot for ChatGPT/Codex.
- `docs/notion-update.md`: copy-paste-ready Notion update if direct Notion update is unavailable.

Refresh generated status:

```powershell
powershell -ExecutionPolicy Bypass -File scripts/update-project-status.ps1
```

## Main Folders

- `state/`: current state for ChatGPT and Codex.
- `reports/`: latest execution report.
- `tasks/`: next Codex task definition.
- `decisions/`: decision history.
- `docs/`: checklist, registry, structure intake, Notion update, and generated status snapshots.
- `scripts/`: local status refresh scripts.
- `templates/`: reusable templates for project repos.

## Current Limitations

- This repo tracks operating docs only; it does not contain application source code.
- Some canonical local project folders may lag GitHub and need sync review before local work continues.
- `job-bom-comparator` still needs GitHub default branch review because GitHub currently reports `codex/source-of-truth-onboarding` as the default branch, while `main` is the intended stable baseline.
- PRG module repos still need continued README/CURRENT_STATE normalization as their contracts and source-of-truth docs mature.
