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
