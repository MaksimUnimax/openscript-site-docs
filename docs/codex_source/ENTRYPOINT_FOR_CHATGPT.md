# ENTRYPOINT FOR CHATGPT

STATUS: CURRENT

Purpose:
- This is the first file ChatGPT must read at the start of a new project dialogue.
- It exists so ChatGPT and Codex use repo memory instead of guessing from prior chat state.

Do not rely on memory before reading this entrypoint.
Repo-level contract note:
- Root `AGENTS.md` is the mandatory repo-level Codex execution contract and must also be followed.
- Public docs source-of-truth is `docs/codex_source/**`.
- Repository metadata, README files, and GitHub-facing files may exist outside that tree and are not application source.

Current canonical project:
- OpenScript / AI Starter Community
- Main site: https://openscript.ru
- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo (separate): /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch for current course/staging work: `design/product-story-03`
- Current accepted app commit for the course work: `f6f5c2b100296efd69c67fa7387550cf2595340d`
- Current accepted app commit for the latest live cabinet/account-blocks/paid-options iteration: `7c94211819ddb334575d7835152637972930d393`
- Current stop-point: the live cabinet/account-blocks/paid-options technical iteration is deployed; manual browser verification is still pending unless the user explicitly confirms acceptance
- Next safe step: manual browser verification of the live cabinet/account-blocks/paid-options behavior, or the next explicit user-selected task
- Kilo/design workflow references are current only for the active design preflight and any later user-approved design runs

Main read path for ChatGPT:
- public docs repo -> `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`

Public docs repo scope:
- source-of-truth docs live under `docs/codex_source/**`
- root `AGENTS.md` is mandatory and may coexist with repo metadata, README, and GitHub-facing files outside that tree
- files outside `docs/codex_source/**` are not application source

Legacy imported history:
- This docs repo also contains legacy OpenScript Agent Lab documentation that was imported before the docs repo was currentized.
- Agent Lab is a separate project.
- Any file referencing `openscript-agent-lab`, `Hermes`, `Fin Instrument`, `Telegram Router`, `youtube_ranked_batch`, or agent-packages is legacy Agent Lab history unless the file header explicitly states otherwise.
- Do not mistake legacy Agent Lab docs for active site documentation.
- The legacy Agent Lab section in `index.yaml` is historical-only and must not be read as the current OpenScript / AI Starter Community site corpus.

Current active docs index:
- `docs/codex_source/index.yaml`

Manifests:
- `docs/codex_source/context/context_manifest.yaml`
- `docs/codex_source/roadmap/roadmap_manifest.yaml`
- `docs/codex_source/module_map/module_map_manifest.yaml`
- `docs/codex_source/project_snapshot/project_snapshot_manifest.yaml`

Project docs:
- `docs/codex_source/project/current_status.md`
- `docs/codex_source/project/project_snapshot.md`
- `docs/codex_source/project/module_map.md`
- `docs/codex_source/project/runtime_git_canon.md`
- `docs/codex_source/project/assistant_codex_workflow_rules.md`
- `docs/codex_source/project/safe_boundaries.md`
- `docs/codex_source/project/source_vs_runtime.md`
- `docs/codex_source/project/technical_spec.md`
- `docs/codex_source/project/project_overview.md`

Instructions:
- Read the current entrypoint before starting a new dialogue.
- For technical tasks, read the active task card and exact required docs.
- For append-only updates, Codex must read manifest + tail only, not the entire large context.
- Do not resume the old Kilo/design workflow automatically; treat it as historical unless the user explicitly selects it.

Read order:
1. `docs/codex_source/index.yaml`
2. `docs/codex_source/project/current_status.md`
3. `docs/codex_source/project/project_snapshot.md`
4. `docs/codex_source/project/module_map.md`
5. `docs/codex_source/context/context_manifest.yaml`
6. `docs/codex_source/roadmap/roadmap_manifest.yaml`
7. `docs/codex_source/module_map/module_map_manifest.yaml`
8. `docs/codex_source/task_cards/<active_task>.yaml` if active_task exists
9. Exact vendor/project docs required by the task card

Notes:
- If the task card is missing or a required doc is still `stub`/`needs_import`, future fix-runs must stop with `STOP_DOCS_MISSING`.
- The project memory layer is separate from application code and separate from vendor docs.
