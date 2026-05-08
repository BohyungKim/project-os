# Decision Log

## 2026-05-08

| Decision | Rationale | Impact |
| --- | --- | --- |
| Integrate the referenced GitHub `AGENTS.md` as adapted local rules instead of copying it verbatim. | John already supplied project-specific Git, state, Notion, and review requirements. A consolidated file avoids duplicated or conflicting instructions. | The local `AGENTS.md` is shorter, project-specific, and easier for future agents to follow. |
| Initialize a local Git repository and work on `docs/agents-guidelines-sync`. | The workspace was empty and not under Git, but John requires feature branch workflow and reviewable state. | Changes can be committed locally, but push/PR remain blocked until a remote origin exists. |
| Provide a copy-paste-ready Notion update instead of updating Notion directly. | Notion tools are available, but the relevant project page was not identified in the request. | John can paste the update into the correct page, and future sessions can update directly once a page ID or URL is provided. |

