# GitHub, Codex, and ChatGPT Source of Truth Setup

This repository is the operating hub for John's beginner-friendly setup where each project uses GitHub as the shared source of truth.

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

## Status Files

- `docs/today-checklist-status.md`: today's setup checklist and evidence.
- `docs/project-registry.md`: discovered local project folders and Git/GitHub state.
- `docs/realtime-repo-status.md`: generated status snapshot for ChatGPT/Codex.
- `docs/notion-update.md`: copy-paste-ready Notion update if direct Notion update is unavailable.

Refresh generated status:

```powershell
powershell -ExecutionPolicy Bypass -File scripts/update-project-status.ps1
```
