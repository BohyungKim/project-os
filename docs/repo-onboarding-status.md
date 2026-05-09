# Repo Onboarding Status

Updated: 2026-05-09 11:52 -04:00

## Summary

| Priority | Project | Current Local Path | Preferred Canonical Local Path | Onboarding Status | Relocation Status | Archive Candidate | Next Action |
| ---: | --- | --- | --- | --- | --- | --- | --- |
| 0 | project-os | `C:\Users\JohnKim\Documents\Codex\2026-05-08\repo-github-codex-chatgpt-source-of` | Same as current | Established | No relocation needed now | No | Review this mapping audit PR |
| 1 | planner-workload-analyzer | `C:\Users\JohnKim\Documents\New project` | `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer` | Established | Relocate later by clean clone from GitHub | Yes, after clone/tests/.env review | Clone canonical folder in separate cleanup task |
| 2 | heater-batch-selection | `C:\Users\JohnKim\Documents\New project 2` | `C:\Users\JohnKim\Desktop\Bins\Projects\heater-batch-selection` | Established | Not audited for relocation yet | Future candidate after clean clone/safety review | Keep manual-review / safe dry-run guardrails |
| 3 | prg-contracts | `C:\Users\JohnKim\Documents\New project 3` | `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts` after PRG split review | Established as contract-only | Do not replace with `PRG` as-is | Yes, only after canonical clone and split review | Decide PRG split before remapping |
| Audit | PRG folder | `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` | Split between `prg-contracts` and a separate PRG app/orchestrator repo | Not established as a repo | Split required | No | Prepare split plan; do not push or read `.env` |
| N/A | project-os legacy sync workspace | `C:\Users\JohnKim\Documents\Codex\2026-05-08\agents-md-role-you-are-working` | None | Do not onboard | Do not relocate | Yes, after John confirmation | Archive later only with explicit approval |

## Current Git Status Summary

At the start of this task:

- Active branch was `codex/correct-local-folder-mapping`.
- Working tree had no uncommitted changes.
- The useful mapping audit changes were already committed on that branch.

Action taken:

- Updated local `main` to current `origin/main`, which includes PR #6.
- Created clean branch `codex/local-folder-mapping-audit`.
- Preserved the useful mapping audit content on the clean branch.

## PRG / prg-contracts Mapping Audit

Current established `prg-contracts` local folder:

- `C:\Users\JohnKim\Documents\New project 3`

Preferred future canonical contract folder:

- `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts`

Requested audit folder:

- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG`

PRG audit result:

- Contract/schema docs exist.
- App/orchestrator/dashboard logic also exists under `src/prg`, `src/prg\templates`, and `scripts`.
- Tests exist under `tests`.
- `.env` exists at the root. Contents were not read.
- No `.git` repo was found, so no remote URL is configured in that folder.

Decision:

- Do not force `PRG` into `prg-contracts` as-is.
- Treat `PRG` as a mixed workspace that needs a split decision.
- Keep the existing contract-only `prg-contracts` mapping until John confirms a split/relocation plan.

## Planner Local Mapping

Current verified folder:

- `C:\Users\JohnKim\Documents\New project`

GitHub source of truth:

- `https://github.com/BohyungKim/planner-workload-analyzer.git`

Preferred canonical folder:

- `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`

Confirmed on 2026-05-09:

- Branch: `main`.
- Local `HEAD`: `7427048 docs: confirm GitHub source of truth`.
- Ahead/behind relative to `origin/main`: `0/0`.
- Working tree: clean.
- `.env` exists locally but is ignored; `.env.example` is tracked.
- Preferred canonical folder does not exist yet.

Recommended cleanup:

- Prefer `git clone https://github.com/BohyungKim/planner-workload-analyzer.git C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`.
- Do not manually move the current folder unless John explicitly approves after confirming there are no needed local-only files.

## Exact Next Prompt

```text
Use project-os main as the central registry.

Task:
Prepare a safe local folder cleanup for planner-workload-analyzer.

Current folder:
C:\Users\JohnKim\Documents\New project

Canonical folder:
C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer

Rules:
- Do not delete or move the old folder yet.
- Clone from GitHub into the canonical folder.
- Run tests from the clone.
- Confirm .env is still local-only and not committed.
- Report whether the old placeholder folder can be archived later.
```

## Notes

- Do not create GitHub repos automatically until John confirms names and ownership.
- Do not push app code until `.env`/secret safety has been verified.
- Do not merge any onboarding or mapping PR without John/ChatGPT review.
