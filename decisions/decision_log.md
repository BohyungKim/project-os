# Decision Log

## 2026-05-08 - Use Repo Status Files As Shared Context

Decision:
- This repo will use tracked state, report, task, and decision files as the shared context layer for ChatGPT and Codex.

Rationale:
- ChatGPT can quickly understand current state from committed files.
- Codex has explicit files to update before finishing future tasks.
- John can review project continuity without relying on chat history alone.

Files:
- `state/current_state.md`
- `state/current_state.json`
- `reports/latest_execution_report.md`
- `tasks/next_codex_task.md`
- `decisions/decision_log.md`

Status:
- Accepted for this setup branch.

Risk:
- These files are useful only if every future Codex task keeps them current.

## 2026-05-08 - Push Blocked Until Remote Exists

Decision:
- Do not invent or guess a GitHub remote for this repo.

Rationale:
- The repo currently has no `origin`.
- John must choose the GitHub owner and private repo name.
- Guessing a remote could push project status to the wrong place.

Status:
- Confirmed by attempted push. `git push -u origin codex/source-of-truth-status-setup` failed because `origin` is not configured.

## 2026-05-08 - Use johnkim4865/project-os As Origin

Decision:
- Configure `origin` as `https://github.com/johnkim4865/project-os.git`.

Rationale:
- John confirmed there is an existing private GitHub repository named `project-os` and provided the exact remote URL.

Status:
- Remote configured locally.
- Push is blocked because GitHub returns `Repository not found` from this shell.

Risk:
- The repo may be private and the current shell credential may not have access, or the URL/owner may need to be rechecked in GitHub.

## 2026-05-08 - Correct Origin To BohyungKim/project-os

Decision:
- Replace the incorrect `johnkim4865/project-os` remote with `https://github.com/BohyungKim/project-os.git`.

Rationale:
- John clarified that the previous remote URL was wrong and provided the correct private repo URL.

Status:
- Accepted and applied locally.
- Branch `codex/source-of-truth-status-setup` pushed successfully.
- Draft PR #2 opened against `main`: `https://github.com/BohyungKim/project-os/pull/2`.

Risk:
- The branch initially had no history in common with remote `main`, so `origin/main` was merged into the feature branch to make the PR possible. This did not merge anything into `main`.
