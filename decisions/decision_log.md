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
- Revalidated on 2026-05-08: `git remote -v` still points to `https://github.com/BohyungKim/project-os.git`, and repeated push returned `Everything up-to-date`.

Risk:
- The branch initially had no history in common with remote `main`, so `origin/main` was merged into the feature branch to make the PR possible. This did not merge anything into `main`.

## 2026-05-08 - project-os Is The Central Registry, Not A Monorepo

Decision:
- Use `project-os` as the central control tower and registry.
- Keep actual application code in separate repositories.

Rationale:
- ChatGPT and Codex need a stable project map, but each real project still needs its own source-of-truth repo.
- This avoids turning `project-os` into a mixed application monorepo.

Status:
- Accepted.
- Registry files added in `codex/central-project-registry`.
- Draft PR #3 opened: `https://github.com/BohyungKim/project-os/pull/3`.

Risk:
- If future work puts app code directly into `project-os`, the central registry could become noisy and less useful.

## 2026-05-08 - Stop Planner Onboarding Until GitHub Repo Exists

Decision:
- Prepare `planner-workload-analyzer` locally, but do not push app code until John creates the target GitHub repo.

Rationale:
- The requested target remote `https://github.com/BohyungKim/planner-workload-analyzer.git` returned repository not found.
- John instructed Codex to stop and report the exact repo URL needed if the GitHub repo does not exist.
- The local app baseline is already committed on `main` as `749ade2 docs: add source-of-truth onboarding files`.

Status:
- Accepted.
- `New project` is locally prepared as the first app source-of-truth repo candidate.
- No app code has been pushed.
- `project-os` registry is being updated to record the blocker.

Risk:
- Starting the second and third project onboarding before this repo is connected could create confusing partial status across multiple local folders.

## 2026-05-09 - Do Not Treat Planner Remote Main As Source Of Truth Yet

Decision:
- Mark `planner-workload-analyzer` as connected but not yet established as a stable source-of-truth repo.
- Do not overwrite or merge unrelated `origin/main` history without explicit John approval.

Rationale:
- `BohyungKim/planner-workload-analyzer` now exists and `origin` is configured.
- Remote `main` already contains unrelated initialization history.
- Normal app `git push -u origin main` was rejected as non-fast-forward.
- Local app baseline was pushed safely to `codex/source-of-truth-baseline` for review without touching `origin/main`.

Status:
- Accepted.
- `project-os` PR #4 is being updated with this status.

Risk:
- If John proceeds to the second project before resolving this first app's `origin/main`, the central registry will show partial onboarding rather than a stable source of truth.

## 2026-05-09 - planner-workload-analyzer Main Is Established

Decision:
- Mark `BohyungKim/planner-workload-analyzer` `main` as the source of truth.

Rationale:
- John explicitly approved replacing the accidental remote `main` history.
- Codex used `git push --force-with-lease origin main`.
- Plain `--force` was not used.
- No unrelated-history merge was performed.
- App `origin/main` now points to `7427048 docs: confirm GitHub source of truth`.
- Temporary branch `codex/source-of-truth-baseline` was deleted.

Status:
- Accepted and completed.
- `project-os` PR #4 is updated with the established status.

Risk:
- Low for planner onboarding. Continue to use feature branches/PRs for future app work.

## 2026-05-09 - Stop Heater Onboarding Until GitHub Repo Exists

Decision:
- Prepare `heater-batch-selection` locally, but do not push app code until John creates the target GitHub repo.

Rationale:
- The requested target remote `https://github.com/BohyungKim/heater-batch-selection.git` returned repository not found.
- John instructed Codex to stop and report the exact repo URL needed if the GitHub repo does not exist.
- The local app baseline is already committed on `main` as `4f5eb1f docs: add heater source-of-truth setup`.
- Browser automation must stay manual-review / safe dry-run only.

Status:
- Accepted.
- `New project 2` is locally prepared as the second app source-of-truth repo candidate.
- No app code has been pushed.
- `project-os` registry is being updated to record the blocker.

Risk:
- Starting the third project before this repo is connected could create confusing partial status across multiple local folders.

## 2026-05-09 - heater-batch-selection Main Is Established

Decision:
- Mark `BohyungKim/heater-batch-selection` `main` as the source of truth.

Rationale:
- John created the empty private GitHub repo.
- Codex added `origin` and pushed local `main`.
- App `origin/main` now points to `6e32db7 docs: confirm heater GitHub source of truth`.
- Tests pass and no blocked secret/local-only/browser artifact files are tracked.
- Browser automation safety rules are documented in the app repo.

Status:
- Accepted and completed.
- `project-os` PR #5 is updated with the established status.

Risk:
- Low for heater onboarding. Future browser automation changes still require explicit safety review.

## 2026-05-09 - Reclassify Third Repo As prg-contracts

Decision:
- Do not onboard `New project 3` as `prg-supply-readiness-checker`.
- Reclassify it as `prg-contracts`, the PRG / Manufacturing Copilot shared contract source-of-truth repo.

Rationale:
- John renamed the target repo to `https://github.com/BohyungKim/prg-contracts.git`.
- The repo should define shared contracts and validation tooling used by feeder modules.
- POBTO readiness, dashboard work, Epicor write-back, and feeder detection logic belong in separate repos/modules.

Status:
- Accepted and implemented.
- `prg-contracts` GitHub `main` is established at `3455eaddc9413acf12f195cd58ad04deaef9a4d0`.

Risk:
- Future prompts may refer to the old supply readiness app name. Codex must follow the contract-only guardrails and avoid building app logic inside `prg-contracts`.

## 2026-05-09 - job-bom-comparator Recommended As First PRG Contract Feeder

Decision:
- Recommend `job-bom-comparator` as the first repo to integrate with `prg-contracts`.

Rationale:
- Comparator output is a natural first feeder for PRGCase.
- `prg-contracts` already contains `examples/comparator_prg_case_sample.json`.
- This allows one small integration to test whether the PRGCase contract is usable before broader Manufacturing Copilot rollout.

Status:
- Recommended next action; not implemented yet.

Risk:
- The exact local/GitHub repo path for `job-bom-comparator` still needs confirmation before implementation.

## 2026-05-09 - Preserve Local Folder Mapping Audit On Clean Branch

Decision:
- Preserve the useful local folder mapping audit changes on `codex/local-folder-mapping-audit`.

Rationale:
- At task start, the active worktree had no uncommitted changes.
- The previously observed audit changes were already committed on `codex/correct-local-folder-mapping`.
- The content is useful because it clarifies current local paths, preferred canonical paths, relocation status, and archive candidates.
- Rebuilding the work on current `origin/main` avoids carrying stale PR #6-era branch context forward.

Status:
- Accepted for this branch.

Risk:
- Low. Documentation-only change, but John should review before any physical folder relocation or archive action.

## 2026-05-09 - Do Not Remap PRG To prg-contracts As-Is

Decision:
- Do not replace the verified contract-only `prg-contracts` working folder with `C:\Users\JohnKim\Desktop\Bins\Projects\PRG` as-is.

Rationale:
- `PRG` contains contract/schema docs, but it also contains app/orchestrator/dashboard logic, scripts, HTML/CSS templates, unit/integration tests, and a root `.env`.
- `PRG` is not currently a Git repository and has no remote URL.
- The established contract-only repo still exists at `C:\Users\JohnKim\Documents\New project 3` and points to `https://github.com/BohyungKim/prg-contracts.git`.

Status:
- Accepted for this registry correction PR.
- `PRG` is recorded as an audit/split candidate, not a direct local-folder replacement.

Risk:
- Forcing `PRG` into `prg-contracts` could mix app logic and local config into a contract-only repo.

## 2026-05-09 - Relocate Planner By Clone, Not Manual Move

Decision:
- Prefer cloning `https://github.com/BohyungKim/planner-workload-analyzer.git` into `C:\Users\JohnKim\Desktop\Bins\Projects\planner-workload-analyzer` over manually moving `C:\Users\JohnKim\Documents\New project`.

Rationale:
- The current planner folder is clean and matches `origin/main` at `7427048`.
- `.env` exists locally and is ignored, so manual moves can accidentally blur source-controlled files with local-only configuration.
- A clean clone verifies GitHub source-of-truth status first and keeps cleanup reversible.

Status:
- Accepted as the recommended future cleanup plan.
- No folder move, rename, delete, or clone was performed in this task.

Risk:
- If the old folder is removed before the clone is verified, John may lose local-only configuration such as `.env`.

## 2026-05-09 - Canonical Project Root Is Desktop Bins Projects

Decision:
- Treat `C:\Users\JohnKim\Desktop\Bins\Projects` as the only canonical local project root.
- Do not default future project mappings to `Documents\New project*` or `Documents\Codex\...`.

Rationale:
- John clarified that all active project directories are under `C:\Users\JohnKim\Desktop\Bins\Projects`.
- The previous registry over-weighted temporary/legacy `Documents` paths and could cause Codex to inspect or update the wrong folder.

Status:
- Accepted and applied to the registry, project map, onboarding status, latest report, next task, and realtime status script.
- Canonical `prg-contracts` clone was created at `C:\Users\JohnKim\Desktop\Bins\Projects\prg-contracts`.

Risk:
- Some established GitHub repos still need canonical clones under the project root.
- `Project-OS` canonical folder exists but is dirty/old and needs sync review before becoming the active Codex workspace.

## 2026-05-09 - Prepare Job BOM Comparator Locally Before GitHub Repo Exists

Decision:
- Prepare `Job BOM Comparator Agent` as the next source-of-truth repo candidate, but do not add an origin or push until John creates `BohyungKim/job-bom-comparator`.

Rationale:
- The canonical local folder exists at `C:\Users\JohnKim\Desktop\Bins\Projects\Job BOM Comparator Agent`.
- The requested target remote `https://github.com/BohyungKim/job-bom-comparator.git` returned repository not found from local git credentials.
- Source-of-truth onboarding files were committed locally on `codex/source-of-truth-onboarding`.
- `.env` was not read and is not tracked.
- Tests pass with 87 tests.

Status:
- Completed.
- John created the empty private repo.
- Codex added `origin` and pushed `codex/source-of-truth-onboarding`.

Risk:
- Existing modified/untracked app/product files remain in the working tree and need separate review before deciding what to push as the app baseline.

## 2026-05-09 - Job BOM Comparator Prepared Branch Pushed, Main Not Promoted

Decision:
- Record `codex/source-of-truth-onboarding` as the pushed Job BOM Comparator source-of-truth candidate branch.
- Do not mark stable `main` as established yet.

Rationale:
- John asked to add origin and push the prepared branch without merging automatically.
- The empty repo accepted the pushed branch.
- No separate `main` base exists yet, and existing app/product changes still need review before stable baseline promotion.

Status:
- Superseded by the later decision to establish `main` from the clean onboarding baseline.

Risk:
- ChatGPT can now inspect the GitHub branch, but John should not treat app `main` as stable until the promotion path is reviewed.

## 2026-05-09 - job-bom-comparator Main Established

Decision:
- Mark `BohyungKim/job-bom-comparator` `main` as established from the clean onboarding baseline.

Rationale:
- The pushed onboarding commit was tested in a clean worktree with 48 passing tests.
- The dirty local working tree also passed 87 tests, but those dirty app/product changes were intentionally kept out of `main`.
- This gives ChatGPT and Codex a stable GitHub branch to use as source of truth while preserving feature work for later review.

Status:
- Accepted and recorded in project-os PR #9.
- `main` and `codex/source-of-truth-onboarding` both point to `ba2ea947f04d56bc8ca5f9a8ffe9879d8ec6234c`.

Risk:
- GitHub default branch still reports `codex/source-of-truth-onboarding`; John may need to switch it to `main` in GitHub settings.

## 2026-05-09 - Review job-bom-comparator App Changes In PR #1

Decision:
- Keep `main` stable and review the app/product change set through PR #1 instead of merging automatically.

Rationale:
- The app/product change set is large and includes docs, UI, correction planning, writer scaffolding, and tests.
- It needs specific review around Epicor write-back and production-impacting boundaries.
- Tests pass, but passing tests are not enough to approve production-impacting behavior.

Status:
- PR #1 opened: `https://github.com/BohyungKim/job-bom-comparator/pull/1`.
- PR #1 is open and mergeable.

Risk:
- Merging PR #1 without review could introduce write-path behavior before John explicitly approves it.
