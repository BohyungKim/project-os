# AGENTS.md

## Project Context
This is an internal engineering automation project.

GitHub is the source of truth:
- `main` is the stable baseline.
- feature branches are Codex work areas.
- pull requests are review areas for Codex and ChatGPT.

## Development Rules
- Keep `main` stable and runnable.
- Use feature branches for Codex work.
- Prefer small, reviewable changes.
- Do not rewrite major architecture without explaining risk.
- Preserve existing user workflow unless explicitly requested.
- Do not modify unrelated files.
- Before changing database, file upload, or Excel export logic, explain migration and rollback risks.
- When improving performance, explain expected impact and how to test it.

## Repo Update Rule
- At the start of work, inspect branch, status, remote, and latest commit.
- At the end of work, report changed files, validation commands, and remaining risk.
- Do not mark work complete unless it is verified by file changes, test results, or clear evidence.
- Keep repo docs updated when behavior, setup, architecture, or operating rules change.

## Communication Rules
- Explain changes for a beginner maintainer.
- Always list affected files.
- Separate confirmed facts from assumptions.
- End with recommended next actions.

## Required Final Output

### Project Case
Case 1 / Case 2 / Case 3

### Current State
[summary]

### Files Changed
[list or "none"]

### Validation
[test command and result, or "not tested yet"]

### Notion Update
[updated directly or copy-paste-ready block]

### Next Codex Task
[one clear next task]

### John Review Required
Yes / No, with reason
