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
  - App branch for current site work: `fix/carousel-arrow-button-visuals`
  - Current site/docs active block: `SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED`
  - Previous accepted public site state: `public_tariff_access_ui_iteration_accepted`
  - Current stop-point: SQLite WAL / busy_timeout source fix is complete and pushed, but the running preview process has not yet been restarted or reloaded. The first future runtime apply/restart must be DB/state backup-gated because WAL activation can mutate SQLite state and create WAL sidecars.
  - Next safe step: `sqlite_wal_busy_timeout_runtime_apply_with_db_backup`
  - The previous `course_practice_carousels_and_vpn_account_block_iteration` block is historical unless the user returns to VPN work
- Isolated course editor work stays under `/opt/ai-starter-community/staging/course-editor/current/` and must not be confused with production app source
- Separate collapsible VPN block after Accounts is requested but not yet proven
- Reported app/source facts tied to the current memory update:
  - `80b8d44d28c21bf5e22cf1674e04c6f5bedcf95b` — Harden login and session defaults
  - `c0b4edf58bab56c2669229b873ab2348cea00c2b` — Add CSRF protection for browser forms
  - `e7fc37d272ca136418dd7e3a175cbbfb5bb03f96` — Revoke sessions on password change
  - `55ad86e6e1ff6b8dd7fbf015fd8e46e72390fa10` — Fix public landing template request context
  - `e29d591039c46fc4651f49281937f0dd564b8750` — Register CSRF helper for materials templates
  - `b9e928b77ccc1dedf92ea28e85d3e1f96dedf928` — Add gated public preview for selected materials drafts
  - `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — Configure SQLite WAL and busy timeout
  - `8a905300739c833ee46ad06383a76d6e65e1c489` — Add tariff typography controls
  - `eb22b091a2a732966c62e24a93c1799babc3440f` — Keep tariff edit page and scale card typography
  - `2ab492d03a472f26a95d836799c132ca35b5e1c1` — Serve Git carousel screenshots from static assets
  - `91a849344708a3629bfb2be2862e78a9cd02c81c` — Polish Git carousel screenshot sizing and labels
  - `4755532dcf186d653f132f1e79d43b11f264a4ea` — Restore Git lesson term emphasis and step one label
  - `56aac56f3eb30f703b86d82fa40e7e33b27cd7de` — Add placeholder carousels to practical lessons
  - `b1e208c4f13f7651772062cb22aaaf6421d4540a` — Add lesson 6 practice carousel
  - `3e8e351564b07c154a887e768b1c37711ffb2634` — Restore account grid and make VPN a real block type
  - `fbb1477a69ee517ff30736326617e5d4b914b320` — Polish VPN panel and account card titles; if this commit is only in a feature/live-synced branch, treat it as pending branch integration until fast-forwarded
  - `a6c0b277b6e6c35def432cf26b630dd02b161a77` — Polish lesson 4 terminology and lesson 5 cabinet link
  - `cf23dda5585e176d9be0075d5e47e557d1ec309d` — Include all referenced course assets in export
  - `56d3f0a1a6be067ea1178f3ef3516fe7ff142a0f` — Export course prompt files and sanitize manifest
- Kilo/design workflow references remain historical unless the user explicitly selects a Kilo-related task

Main read path for ChatGPT:
- public docs repo -> `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`

Public docs repo scope:
- source-of-truth docs live under `docs/codex_source/**`
- root `AGENTS.md` is mandatory and may coexist with repo metadata, README, and GitHub-facing files outside that tree
- files outside `docs/codex_source/**` are not application source

Current active docs index:
- `docs/codex_source/index.yaml`

Manifests:
- `docs/codex_source/context/context_manifest.yaml`
- `docs/codex_source/roadmap/roadmap_manifest.yaml`
- `docs/codex_source/module_map/module_map_manifest.yaml`
- `docs/codex_source/project_snapshot/project_snapshot_manifest.yaml`

Project docs:
- `docs/codex_source/project/current_status.md`
- `docs/codex_source/project/account_blocks.md`
- `docs/codex_source/project/paid_options_activation.md`
- `docs/codex_source/materials/COURSE_LESSON_MAP.md`
- `docs/codex_source/materials/MATERIALS_SPEC.md`
- `docs/codex_source/materials/COURSE_METHOD_SPEC.md`
- `docs/codex_source/project/safe_boundaries.md`
- `docs/codex_source/project/source_vs_runtime.md`
- `docs/codex_source/project/technical_spec.md`

Instructions:
- Read the current entrypoint before starting a new dialogue.
- For technical tasks, read the active task card and exact required docs.
- For append-only updates, Codex must read manifest + tail only, not the entire large context.
- Do not resume the old Kilo/design workflow automatically; treat it as historical unless the user explicitly selects it.
- For the current site stage, trust `index.yaml` current dialogue state and the current manifests/current docs over old legacy/imported files.
- Legacy/imported files are not required current startup docs unless a future task explicitly targets legacy cleanup or import repair.

Read order:
1. `docs/codex_source/index.yaml`
2. `docs/codex_source/project/current_status.md`
3. `docs/codex_source/context/context_manifest.yaml`
4. `docs/codex_source/context/current_dialogue_context.md`
5. `docs/codex_source/roadmap/roadmap_manifest.yaml`
6. `docs/codex_source/roadmap/imported/roadmap_v0_1_initial_site_baseline.md`
7. `docs/codex_source/module_map/module_map_manifest.yaml`
8. `docs/codex_source/module_map/module_map.md`
9. `docs/codex_source/project/account_blocks.md`
10. `docs/codex_source/materials/COURSE_LESSON_MAP.md`
11. `docs/codex_source/materials/MATERIALS_SPEC.md`
12. `docs/codex_source/materials/COURSE_METHOD_SPEC.md`
13. `docs/codex_source/project/safe_boundaries.md`
14. `docs/codex_source/project/source_vs_runtime.md`
15. `docs/codex_source/project/technical_spec.md`
16. `docs/codex_source/task_cards/<active_task>.yaml` if active_task exists
17. Exact vendor/project docs required by the task card

Notes:
- If the task card is missing or a required doc is still `stub`/`needs_import`, future fix-runs must stop with `STOP_DOCS_MISSING`.
- The project memory layer is separate from application code and separate from vendor docs.

Legacy / not current startup sources:
- `docs/codex_source/project/project_snapshot.md`
- `docs/codex_source/project/project_overview.md`
- `docs/codex_source/project/runtime_git_canon.md`
- `docs/codex_source/project/assistant_codex_workflow_rules.md`
- `docs/codex_source/project/module_map.md`

These files may still exist as imported history, legacy reference, or stub/needs-import material.
They must not be treated as required current startup docs and must not trigger a startup STOP when they are not part of the active current-docs set.
They may be read only when a future task explicitly targets legacy cleanup or import repair.
