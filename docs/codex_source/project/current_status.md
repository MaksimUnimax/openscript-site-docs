# Current status — OpenScript / AI Starter Community

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community
UPDATED: 2026-06-08
CURRENT_STATUS_ID: CURRENT_STATUS_20260608_COURSE_ORDER_AND_FINAL_SECTION_REPAIR

## Repository separation

- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: design/product-story-03
- Production site: https://openscript.ru

## Current active block

Docs repo memory update for the verified current course order and final section.

## Verified source inspection

- `source/app/materials/course_content/drafts/dair_smoke_20260529/index.html`
- `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- `source/tests/test_course_rendering.py`

## Accepted course baseline

- Accepted app course commit: `f6f5c2b100296efd69c67fa7387550cf2595340d`
- Lesson 4 title: `Codex, AGENTS.md, Skills, токены и роль модели`
- Lesson 5 title: `PowerShell, Terminal и подключение к серверу`
- Lesson 6 title: `Старт проекта: сначала документация, потом разработка`
- Lesson 7 title: `Процесс работы`
- Course has 9 numbered lessons plus a visible final section (`lesson-10`).

## Current lesson 7 scope

- `run`, `design run`, `fix run`, `proof run`
- one-run/one-task control logic
- `context` and `context window`
- `prefix`-extension practice
- starter prompt panel with `Смотреть prompt`, `Скопировать prompt`, `Скачать .md`, and a readonly textarea preview

## Legacy bridge reclassification

- `docs/codex_source/project/module_map.md`, `docs/codex_source/project/project_snapshot.md`, and `docs/codex_source/project/project_overview.md` are legacy/imported history, not current site memory.
- Current site module map: `docs/codex_source/module_map/module_map.md`.
- Current site status: `docs/codex_source/project/current_status.md` and `docs/codex_source/project/CURRENT_STATUS.md`.

## Current stop-point

The current app course baseline remains the accepted lesson 7 rewrite, with the 4/5/6 order and final section verified from source.
Next safe app step remains the proof-only design workflow preflight.
