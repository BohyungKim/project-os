# Nightly Automation Prompt

Use this for the first low-risk nightly automation.

```text
Review this repository every night.
Do not modify source code.
Create a nightly engineering intelligence report.

Include:
1. recent changes summary
2. risky areas
3. missing tests
4. documentation updates needed
5. top 3 actions for John tomorrow

If code changes are needed, write a proposal only.
If documentation updates are low risk, draft them in docs/nightly_suggestions/YYYY-MM-DD.md.
Never merge automatically.
```

Recommended rule:
- Start with reports only.
- Allow docs drafts only after John approves the automation behavior.
- Do not allow automatic source code edits until the project has stable tests and branch protection.
