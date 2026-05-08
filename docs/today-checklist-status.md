# Today Checklist Status

Date: 2026-05-08
Owner: John
Purpose: Set up GitHub as the source of truth for Codex and ChatGPT.

## Checklist

| Item | Status | Evidence / Notes |
| --- | --- | --- |
| GitHub Desktop or Git CLI installed | Confirmed | Git CLI: `git version 2.52.0.windows.1`. GitHub Desktop exists at `C:\Users\JohnKim\AppData\Local\GitHubDesktop\GitHubDesktop.exe`. |
| Create private GitHub repos per project | John review required | No `gh` CLI or GitHub token is available in this shell. Current GitHub plugin tools do not expose repo creation. Create private repos in GitHub Desktop or GitHub web. |
| Connect local project folders to GitHub repos | Not complete | Found local git folders, but no remotes were configured for `C:\Users\JohnKim\Documents\New project`, `New project 2`, or `New project 3`. |
| Confirm each repo's `main` branch is runnable and stable | Not complete | Discovered local projects are on `master` with no commits, so there is no confirmed stable `main` baseline yet. |
| Create root `AGENTS.md` | Completed for this operating repo | Created `AGENTS.md` in this repo and `templates/AGENTS.project.md` for project repos. |
| Confirm Codex GitHub connection | Partially confirmed | GitHub plugin tools are available for file and PR work, but repo creation/list tools are not exposed. |
| Confirm Codex can see each repo | Local only | Codex can inspect local folders under `C:\Users\JohnKim\Documents`; GitHub remote access awaits repo creation/remotes. |
| Set Codex work to feature branch / PR, not `main` | Completed as operating rule | Added to `AGENTS.md`, `README.md`, and project template. |
| Confirm ChatGPT GitHub connector repo access | John review required | This must be checked from ChatGPT after the GitHub repos exist and are connected to the connector. |
| Ask ChatGPT for main-based architecture summary | Ready after remote setup | Prompt is documented in `README.md`. |
| Ask ChatGPT for PR/diff-based change review | Ready after PR setup | Prompt is documented in `README.md`. |

## Current Result

Confirmed:
- Git is installed.
- GitHub Desktop is installed locally.
- Notion access is available.
- Existing local git folders were discovered.
- The current operating folder was not a git repo at task start.
- The current operating folder has now been initialized as a local git repo on `main`.
- Initial source-of-truth docs have been committed locally.

Incomplete:
- GitHub private repos still need to be created.
- Local projects need remotes.
- Existing local projects need first commits and branch normalization from `master` to `main`.
- ChatGPT GitHub connector access must be verified from ChatGPT.
- This operating repo still needs a GitHub remote and push.

Uncertain:
- Which discovered folders map to John's named projects.
- Which GitHub owner/account should own the private repos.
- Whether `New project`, `New project 2`, and `New project 3` are the intended project folders.

## Recommended Manual GitHub Desktop Step

For each project folder:

1. Open GitHub Desktop.
2. Add the local repository folder.
3. Publish repository.
4. Choose Private.
5. Name the repo using lowercase and hyphens.
6. Confirm the default branch is `main`.

After that, ask Codex:

```text
For this repo, run the GitHub source-of-truth intake.
Confirm branch, remote, current status, AGENTS.md, runnable main, and the next safe feature-branch task.
```
