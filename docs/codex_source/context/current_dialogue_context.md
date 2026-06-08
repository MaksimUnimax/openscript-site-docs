# Current dialogue context — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531

This file is append-only.

Do not rewrite historical blocks destructively.

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_INITIAL_SOURCE_BASELINE source=codex_sync -->
## 2026-05-31 — Initial source-derived documentation baseline imported

This run imported the first source-derived documentation baseline for the OpenScript / AI Starter Community site project.

### Documentation created/updated

- project/current_status.md — site-specific current status
- project/technical_spec.md — initial source-derived technical spec
- module_map/module_map.md — site-specific module map
- module_map/module_map_manifest.yaml — site manifest
- module_map/imported/current_module_map_snapshot.md — detailed module snapshot
- roadmap/roadmap_manifest.yaml — site roadmap manifest
- roadmap/imported/roadmap_v0_1_initial_site_baseline.md — initial roadmap
- project/safe_boundaries.md — site-specific safe boundaries
- project/source_vs_runtime.md — site-specific source vs runtime rules
- project/import_queue/missing_sources.yaml — site-specific missing items
- context/context_manifest.yaml — updated for site
- context/current_dialogue_context.md — this append block

### Source-derived facts

- Stack: FastAPI + Jinja2 + SQLite + bcrypt + uvicorn
- All implemented modules: core, auth, admin, landing, materials, cabinet, tariffs, paid_options, notifications, shared
- Structure-only modules: payments, ai_sales_agent (NOT_YET_PROVEN)
- Auth includes registration (currently closed), email verification, cookie sessions, password reset
- App on branch design/product-story-03, 9 untracked files

### Next step

Design and create a staging/test environment before any app source changes.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_INITIAL_SOURCE_BASELINE -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_STAGING_IMPLEMENTATION source=codex_sync -->
## 2026-05-31 — Staging environment implemented

### App repo changes

- .gitignore — added staging/data/* and staging/runtime/* ignore rules
- staging/start.sh — staging startup script (bash -n validated)
- staging/env.staging.example — non-secret env var template
- staging/README.md — staging usage and safety instructions
- staging/data/.gitkeep — placeholder for isolated SQLite database
- staging/runtime/.gitkeep — placeholder for isolated runtime files

### Docs repo changes

- project/staging_environment.md — staging environment description
- project/staging_proof.md — staging isolation proof
- project/safe_boundaries.md — updated with staging paths
- project/source_vs_runtime.md — updated with staging layer
- project/current_status.md — updated with staging status
- project/import_queue/missing_sources.yaml — staging items marked done
- context/context_manifest.yaml — updated append tracking
- context/current_dialogue_context.md — this append block

### Key facts

- Staging created with zero core source code changes (env-driven config only).
- Staging binds to 127.0.0.1:8090 with isolated SQLite database.
- start.sh was NOT executed — staging is not running.
- No production runtime touched.
- Agent Lab repos untouched.

### Current blocker

Staging is created but has NOT been started or verified.
Next safe step: start staging locally and verify /healthz endpoint.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_STAGING_IMPLEMENTATION -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_HEALTH_PROOF source=codex_sync -->
## 2026-05-31 — Staging health proof successful

### Health check results

- start.sh was fixed to use source/.venv/bin/python (project virtual environment)
- Staging started on 127.0.0.1:8090
- Listener confirmed on 127.0.0.1:8090 only
- /healthz returned: {"ok":true,"service":"ai-starter-community"}
- /readyz returned: {"ok":true,"ready":true}
- Staging process stopped after health check
- Port 8090 confirmed free after stop

### Files changed

- staging/start.sh — added virtual environment detection (committed and pushed)
- project/staging_proof.md — updated PROVEN_RUNTIME
- project/current_status.md — updated healthy status
- context/current_dialogue_context.md — this append block
- context/context_manifest.yaml — updated append tracking

### Key facts

- No source/app/** changed
- No source/tests/** changed
- No production state/runtime/logs/backups changed
- Agent Lab repos untouched
- Staging is ready for design/Kilo workflow runs
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_HEALTH_PROOF -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_SYNC source=codex_sync -->
## 2026-05-31 — Docs synchronized after staging health proof

### Files updated in this sync

- project/current_status.md — updated HEAD to 6fae69f, added completed runs, added current active block, decisions, open questions
- roadmap/roadmap_manifest.yaml — updated phases: Stage 2 completed, Stage 3 active (Design/Kilo)
- roadmap/imported/roadmap_v0_1_initial_site_baseline.md — restructured to 6 stages, Stage 2 marked health-proven
- project/source_vs_runtime.md — added staging support scripts as source of truth
- project/import_queue/missing_sources.yaml — updated staging items to health-proven, added Kilo workflow config placeholder
- context/context_manifest.yaml — updated append tracking
- context/current_dialogue_context.md — this append block

### Current active block

Design/Kilo workflow for OpenScript / AI Starter Community through proven staging/test contour.

### Roadmap stages

- Stage 0 — Repo separation and AGENTS bootstrap: COMPLETED
- Stage 1 — Site docs currentization and source-derived baseline: COMPLETED
- Stage 2 — Isolated staging/test contour: COMPLETED and HEALTH-PROVEN (healthz/readyz on 127.0.0.1:8090)
- Stage 3 — Design/Kilo workflow on staging: NEXT
- Stage 4 — Manual review and screenshot proof: LATER
- Stage 5 — Production handoff: LATER, separate approval required

### Not next

- Production deploy
- Payment implementation
- AI Sales Agent implementation
- Agent Lab work
- Docs cleanup of Agent Lab
- App refactor
- nginx/systemd
- Public staging exposure
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_SYNC -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_COURSE_LESSONS_20260603 source=codex_sync -->
## 2026-06-03 — Course lessons 1–9 semantic blocks accepted

This run currentized the site/course dialogue state after the accepted course lesson refinement work.

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: design/product-story-03

### Final accepted app state

- Latest accepted app commit: a5a2f6ef40338959a659bc9feecf0a23c46a0c70
- Commit title: Add semantic lesson blocks
- Changed file: source/app/materials/course_content/drafts/dair_smoke_20260529/script.js
- Public GitHub showed 1 file changed, 916 additions, 10 deletions
- Previous accepted app commit immediately before the final block split: a7458df00e3b42b09cfcdffae1d14e90be43f028

### Accepted course implementation facts

- Lessons 1–9 are now split into semantic blocks/cards.
- `renderLessonBlocks` supports `section.blocks` as `callout lesson-content-block` cards.
- Fallback to old `contentHtml` remains for lessons without blocks.
- Lesson 4 keeps the starter prompt controls:
  - Перейти к стартовому prompt
  - Смотреть prompt
  - Скопировать prompt
  - Скачать .md
- Copy/download buttons remain visible.
- Only the prompt textarea is hidden/collapsed by default.
- Lesson 4 deploy-key wording was corrected so the private key stays on the server, the public key goes to GitHub Deploy keys, and the user returns with confirmation only.
- `starterPromptMarkdown` formatting was intentionally not repaired in the accepted final app run.

### Current stop-point

Course lesson semantic-block UI/content pass is accepted by the user.
Docs update is now required to bring the public docs repo current.

### Next safe step

Wait for the user-selected next task after this docs update.
Do not resume the old Kilo/design workflow automatically.

### Historical correction

Any older Kilo/design workflow references are historical unless the user explicitly chooses Kilo.
<!-- CONTEXT_APPEND_END id=CTX_SITE_COURSE_LESSONS_20260603 -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY source=codex_sync -->
## CTX_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY

- Public docs were stale relative to accepted app course work.
- Course lesson refinement is accepted through app commit f6f5c2b100296efd69c67fa7387550cf2595340d.
- Lesson 7 was renamed to "Процесс работы" and now covers run types, control of Codex, context window, and prefix-extension practice.
- Staging/test contour remains proven and localhost-only.
- Next user-selected technical direction is Design/Kilo workflow preparation.
- The next run must be proof-only preflight and must not patch UI yet.
- Agent Lab remains no-touch.
- Production remains no-touch.
- No secrets may be read.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260608_SITE_DOCS_CURRENT_STATE_SYNC source=codex_sync -->
## 2026-06-08 — Site docs current-state sync verified from local source

### Verified app course baseline

- `source/app/materials/course_content/drafts/dair_smoke_20260529/index.html`
- `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- `source/tests/test_course_rendering.py`
- accepted app commit: `f6f5c2b100296efd69c67fa7387550cf2595340d`
- current lesson 7 title: `Процесс работы`

### Verified current course facts

- course has 9 lessons;
- lesson 7 covers `run`, `design run`, `fix run`, `proof run`, `context`, `context window`, and `prefix`-extension practice;
- lesson 7 includes a starter prompt panel with copy/download actions and a readonly textarea preview;
- lesson 6 has the starter prompt panel for project documentation start;
- lesson 8 has starter prompt panels for docs update and new dialogue;
- no visible lesson 10 exists in the current source.

### Docs repair result

- stale uppercase current status, roadmap, lesson map, materials spec, course method spec, and decisions were synchronized to the current lesson 7 state;
- legacy Agent Lab / YouTube bridge docs were marked as legacy/imported, not current site state;
- current safe next app step remains the proof-only design workflow preflight;
- no app source was changed.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260608_SITE_DOCS_CURRENT_STATE_SYNC -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260608_COURSE_ORDER_AND_FINAL_SECTION_REPAIR source=codex_sync -->
## 2026-06-08 — Course order and final section repaired from source

### Verified current source truth

- Lesson 4: `Codex, AGENTS.md, Skills, токены и роль модели`
- Lesson 5: `PowerShell, Terminal и подключение к серверу`
- Lesson 6: `Старт проекта: сначала документация, потом разработка`
- Lesson 7: `Процесс работы`
- Final section: `lesson-10` / `Финал курса`

### Verified current course wording

- The course has 9 numbered lessons plus a visible final section.
- Lesson 6 owns the starter prompt for project documentation start.
- Lesson 7 owns the starter prompt for prefix-extension practice.
- Lesson 8 owns the starter prompts for docs update and new dialogue.

### Repair result

- Previous course-order statements that treated 4/5/6 as start project / Codex / PowerShell are superseded.
- Previous wording that said there was no visible lesson 10 is superseded.
- Current docs should use the 9 numbered lessons plus final section wording.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260608_COURSE_ORDER_AND_FINAL_SECTION_REPAIR -->
