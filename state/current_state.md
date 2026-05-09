# Current State

Updated at: 2026-05-09 10:56 America/Toronto

## Project Case

Case 3 - Codex Continuation Sync.

## Current Phase

Second app repo onboarding, blocked on GitHub repo creation.

## Confirmed

- PR #4 is merged into `project-os/main`.
- `project-os/main` reflects `planner-workload-analyzer` as established.
- Current `project-os` branch: `codex/heater-onboarding-status`.
- `project-os` remote: `https://github.com/BohyungKim/project-os.git`.
- Second app project folder: `C:\Users\JohnKim\Documents\New project 2`.
- Second app target repo: `BohyungKim/heater-batch-selection`.
- `New project 2` branch was renamed from `master` to `main` because it had no commits yet.
- `New project 2` now has a local onboarding baseline commit: `4f5eb1f docs: add heater source-of-truth setup`.
- `New project 2` has no GitHub remote configured.
- `git ls-remote https://github.com/BohyungKim/heater-batch-selection.git` returned repository not found.
- No app code was pushed to GitHub.
- No tracked `.env`, credentials, tokens, API keys, passwords, or local-only files were found.
- `python -m pytest` passed 9 tests in `New project 2`.
- Playwright/NepConnect automation remains manual-review / safe dry-run only.

## Changed

- Added project-level source-of-truth files to `New project 2`.
- Improved `New project 2/.gitignore` for secret, local-only, browser artifact, generated output, log, and temp exclusions.
- Updated `New project 2/README.md` with browser automation safety rules.
- Committed the local heater app baseline.
- Updated `project-os` registry/status files to record the heater onboarding result and GitHub repo blocker.

## Still Incomplete

- John must create the empty private GitHub repo `BohyungKim/heater-batch-selection`.
- After the repo exists, Codex still needs to add it as `origin`, push `main`, and open a PR if applicable.
- `prg-supply-readiness-checker` onboarding has not started yet.

## Uncertain

- Whether John wants the local folder `New project 2` renamed to `heater-batch-selection`.
- Whether the first GitHub push should go directly to `main` or use a setup branch after the empty repo exists.

## Validation Evidence

Commands run:

```powershell
python -m pytest
Get-Content state/current_state.json | ConvertFrom-Json
git diff --check
git check-ignore -v .env .env.local out/demo/results.json screenshots/a.png downloads/file.pdf storageState.json trace.har traces/run.trace.zip .auth/state.json logs/run.log tmp/a.txt temp/a.txt
```

Results:
- `New project 2`: 9 tests passed.
- `New project 2`: tracked secret/local-only scan found 0 blocked files.
- `New project 2`: ignore checks confirmed representative secret, browser artifact, output, log, and temp paths are ignored.
- `New project 2`: `state/current_state.json` parsed successfully.
- `New project 2`: `git diff --check` passed.
- Target GitHub repo is not available yet.

## Current Risk

The second app project is locally prepared, but it is not a GitHub source of truth until John creates `BohyungKim/heater-batch-selection` and Codex pushes the baseline. Browser automation remains the main safety risk and must not automate login, purchasing, submission, or production-impacting actions without explicit approval.
