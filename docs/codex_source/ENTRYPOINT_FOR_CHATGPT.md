# ENTRYPOINT FOR CHATGPT

STATUS: initial

Purpose:
- This is the first file ChatGPT must read at the start of a new project dialogue.
- It exists so ChatGPT and Codex use repo memory instead of guessing from prior chat state.

Do not rely on memory before reading this entrypoint.

Current canonical project:
- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo (separate): /opt/ai-starter-community
- Production site: https://openscript.ru
- Main read path for ChatGPT: public docs repo -> `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`
- Public docs repo contains only `docs/codex_source/**`: yes

This repo head: ceffeb25aef0d54d42efda1aa5394cd9b484ae6c

Legacy imported history:
This docs repo also contains legacy OpenScript Agent Lab documentation that was imported before the docs repo was currentized. Agent Lab is a separate project. Any file referencing `openscript-agent-lab`, `Hermes`, `Fin Instrument`, `Telegram Router`, `youtube_ranked_batch`, or agent-packages is legacy Agent Lab history unless the file header explicitly states otherwise. Do not mistake legacy Agent Lab docs for active site documentation.

Current active docs index:
- docs/codex_source/index.yaml

Manifests:
- docs/codex_source/context/context_manifest.yaml
- docs/codex_source/roadmap/roadmap_manifest.yaml
- docs/codex_source/module_map/module_map_manifest.yaml
- docs/codex_source/project_snapshot/project_snapshot_manifest.yaml

Vendor docs index:
- docs/codex_source/vendor/hermes/README.md
- docs/codex_source/vendor/telegram/README.md
- docs/codex_source/index.yaml

Project docs:
- docs/codex_source/project/README.md
- docs/codex_source/project/current_status.md
- docs/codex_source/project/project_snapshot.md
- docs/codex_source/project/module_map.md
- docs/codex_source/project/runtime_git_canon.md
- docs/codex_source/project/assistant_codex_workflow_rules.md
- docs/codex_source/project/safe_boundaries.md
- docs/codex_source/project/source_vs_runtime.md
- docs/codex_source/project/technical_spec.md
- docs/codex_source/project/project_overview.md

Instructions:
- Vendor docs are under `docs/codex_source/vendor/**`.
- Roadmap/context are historical/project memory, not vendor source-of-truth.
- For technical tasks, read the active task card and exact required docs.
- For append-only updates, Codex must read manifest + tail only, not the entire large context.

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
