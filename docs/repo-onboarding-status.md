# Repo Onboarding Status

Updated: 2026-05-09 11:37 -04:00

## Summary

| Priority | Project | Recommended GitHub Repo | Onboarding Status | Blocker | Next Action |
| ---: | --- | --- | --- | --- | --- |
| 0 | project-os | `BohyungKim/project-os` | Established | None for registry foundation | Review local folder mapping correction PR |
| 1 | planner-workload-analyzer | `BohyungKim/planner-workload-analyzer` | Established | Local folder still uses placeholder name `New project` | Relocate later by clone from GitHub to `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer` |
| 2 | heater-batch-selection | `BohyungKim/heater-batch-selection` | Established | Browser automation safety review remains ongoing | Keep manual-review / safe dry-run guardrails |
| 3 | prg-contracts | `BohyungKim/prg-contracts` | Established as contract-only at `C:\Users\JohnKim\Documents\New project 3` | Requested `PRG` remap is not safe as-is | John review: decide PRG split before changing local mapping |
| Audit | PRG folder | Split needed before repo assignment | Not established as a repo | Contains app/orchestrator/dashboard logic, tests, templates, scripts, and `.env`; no `.git` repo | Split contract/schema docs from app logic before any remap |
| N/A | project-os legacy sync workspace | None | Do not onboard | Duplicate project-os workspace | Archive after John confirmation |

## Planner Local Mapping

Current verified folder:

- `C:\Users\JohnKim\Documents\New project`

GitHub source of truth:

- `https://github.com/BohyungKim/planner-workload-analyzer.git`

Confirmed on 2026-05-09:

- Branch: `main`.
- Local `HEAD`: `7427048 docs: confirm GitHub source of truth`.
- `origin/main`: `7427048 docs: confirm GitHub source of truth`.
- Ahead/behind relative to `origin/main`: `0/0`.
- Working tree: clean.
- `.env` exists locally but is ignored; `.env.example` is tracked.

Recommended cleanup:

- Prefer `git clone https://github.com/BohyungKim/planner-workload-analyzer.git C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer`.
- Do not manually move the current folder unless John explicitly approves after confirming there are no needed local-only files.

## PRG / prg-contracts Mapping Audit

Current established `prg-contracts` local folder:

- `C:\Users\JohnKim\Documents\New project 3`

GitHub source of truth:

- `https://github.com/BohyungKim/prg-contracts.git`

Requested audit folder:

- `C:\Users\JohnKim\Desktop\Bins\Projects\PRG`

PRG audit result:

- Contract/schema docs exist.
- App/orchestrator/dashboard logic also exists under `src/prg`, `src/prg\templates`, and `scripts`.
- Tests exist under `tests`.
- `.env` exists at the root.
- No `.git` repo was found, so no remote URL is configured in that folder.

Decision:

- Do not force `PRG` into `prg-contracts` as-is.
- Treat `PRG` as a mixed workspace that needs a split decision.
- Keep the existing contract-only `prg-contracts` mapping until John confirms a split/relocation plan.

## Exact Next Prompt

```text
Use project-os as the central registry.

Review the PRG split decision.

Audit:
C:\Users\JohnKim\Desktop\Bins\Projects\PRG

Goal:
Decide what belongs in BohyungKim/prg-contracts and what belongs in a separate PRG app/orchestrator repo.

Do not move, rename, delete, or push folders.
Do not read .env contents.
Do not modify application logic.
Prepare a split plan with exact files and validation steps.
```

## Notes

- Do not create GitHub repos automatically until John confirms names and ownership.
- Do not push app code until `.env`/secret safety has been verified.
- Do not merge any onboarding PR without John/ChatGPT review.
