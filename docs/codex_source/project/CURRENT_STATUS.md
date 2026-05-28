# Current Status

## Known current live app

Main app repo:

`/opt/ai-starter-community`

Main site:

`https://openscript.ru`

Service:

`ai-starter-community-preview.service`

Known public checks from previous inventory:
- `/` returns 200;
- `/healthz` returns 200;
- `/readyz` returns 200.

## Known app features from prior work

- FastAPI modular app foundation exists.
- Registration exists.
- Email verification exists.
- Login/logout exists.
- Password reset exists.
- Roles exist.
- Admin foundation exists.
- Tariffs exist.
- Paid options exist.
- “Работа с ИИ” materials placeholder exists.
- SMTP via Yandex was enabled in previous work.
- Domain and HTTPS were connected.
- Payment is not implemented yet.
- AI-sales agent is not implemented yet.

## Current documentation problem

The main app repo lacks a complete canonical docs/source-of-truth package.
The new docs repo solves this.

## Not in scope now

- no live site changes;
- no app code changes;
- no payment implementation;
- no Agent Lab work;
- no APM work;
- no nginx/systemd/env changes;
- no course HTML generation yet.

## Update 2026-05-28 — Docs repo bootstrap completed and next stage

### Confirmed

- The documentation/source-of-truth repo for the main OpenScript / AI Starter Community site exists at `/opt/openscript-site-docs`.
- The public GitHub repo exists at `https://github.com/MaksimUnimax/openscript-site-docs`.
- The repo describes the main OpenScript / AI Starter Community website, not a standalone course-only product.
- The main app repo remains `/opt/ai-starter-community`.
- The public site remains `https://openscript.ru`.
- Root `AGENTS.md` exists.
- `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md` exists.
- `docs/codex_source/index.yaml` exists.
- The initial docs package exists under `docs/codex_source/**`.
- External reference docs were downloaded for DAIR lesson-generator, ClassBuild, HyperFrames, Skill-Anything, LiaScript, and a Codex Skills stub.
- GitHub push for the docs repo succeeded.
- A deploy key for `openscript-site-docs` was created and added with write access.
- The deploy-key explanation was added to `docs/codex_source/materials/COURSE_LESSON_MAP.md` inside Lesson 7 “Git простыми словами”.
- The deploy-key lesson update was pushed at commit `8d3036e94f5bbd3b2abddbce11642200568eab83`.

### Current active block

Bring the OpenScript site documentation into a clean canonical state after bootstrap.

### Current blocker

The repo contains the initial documentation skeleton, but many documents are still initial/stub and need content refinement. The course is still represented mostly as a lesson map, not a full student-ready curriculum.

### Current next step

Run docs refinement for:
- canonical TZ;
- roadmap;
- context;
- current status;
- decisions;
- module map;
- user/admin/materials flows;
- course lesson map;
- materials/course docs.

### Not next

Do not start:
- app implementation;
- live site changes;
- payment implementation;
- course HTML generation;
- Agent Lab work;
- APM work;
- OpenDesign Lab work.

Before any app work, first run read-only proof for `/opt/ai-starter-community`.
