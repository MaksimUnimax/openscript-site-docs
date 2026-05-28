# Roadmap

## Stage 0 — Documentation source-of-truth repo

Goal:
Create separate docs repo for the main OpenScript site.

Deliverables:
- README.md
- AGENTS.md
- ENTRYPOINT_FOR_CHATGPT.md
- index.yaml
- project docs
- app docs
- workflow docs
- landing docs
- materials/course docs
- tools reference docs
- server inventory docs

Status:
Current stage.

## Stage 1 — Main docs consolidation

Goal:
Turn uploaded context/TZ/roadmap fragments into clean canonical docs.

Deliverables:
- PROJECT_OVERVIEW.md
- TZ.md
- ROADMAP.md
- CONTEXT.md
- CURRENT_STATUS.md
- DECISIONS.md
- MODULE_MAP.md
- USER_FLOWS.md

## Stage 2 — Live app state proof

Goal:
Read-only proof of current `/opt/ai-starter-community` state.

Deliverables:
- updated SERVER_INVENTORY.md
- updated LOCAL_GIT_SNAPSHOT.md
- current branch/HEAD/status
- current modules/routes summary

## Stage 3 — Landing/main page continuation

Goal:
Continue product landing work only after docs are canonical.

Deliverables:
- homepage spec
- accepted design branch decision
- main integration plan

## Stage 4 — Materials and course inside cabinet

Goal:
Design paid materials area and first course inside “Работа с ИИ”.

Deliverables:
- MATERIALS_SPEC.md
- COURSE_METHOD_SPEC.md
- COURSE_LESSON_MAP.md
- COURSE_VISUAL_SYSTEM.md

## Stage 5 — Payment plan

Goal:
Design payment flow and activation model.

Deliverables:
- PAYMENTS_PLAN.md
- provider choice
- admin/payment flow
- activation rules

## Stage 6 — AI-sales agent

Goal:
Design AI-sales assistant for landing/funnel.

Deliverables:
- AI_SALES_AGENT_PLAN.md

## Stage 0 update — Completed bootstrap chain

### Stage 0.0 — Docs repo bootstrap

Status: completed.

Result:
- `/opt/openscript-site-docs` created.
- Initial source-of-truth structure created.
- Root `AGENTS.md` created.
- `ENTRYPOINT_FOR_CHATGPT.md` created.
- `index.yaml` created.
- Initial project/app/landing/materials/workflow/server/tools docs created.
- External reference docs downloaded.

### Stage 0.1 — GitHub remote and deploy key

Status: completed.

Result:
- Public GitHub repo created:
  `https://github.com/MaksimUnimax/openscript-site-docs`
- Deploy key created for this repo.
- Deploy key added with write access.
- Push to `origin/main` succeeded.

### Stage 0.2 — Deploy-key explanation in course Git lesson

Status: completed.

Result:
- Deploy-key explanation added to:
  `docs/codex_source/materials/COURSE_LESSON_MAP.md`
- Placement:
  Lesson 7 — Git простыми словами.
- Commit:
  `8d3036e94f5bbd3b2abddbce11642200568eab83`

### Stage 1 — Documentation refinement

Status: current next stage.

Goal:
Turn the bootstrap docs into useful canonical docs for the main OpenScript / AI Starter Community website.

Targets:
- TZ;
- roadmap;
- context;
- current status;
- decisions;
- module map;
- user flows;
- admin flows;
- materials flow;
- tariffs/options flow;
- course method spec;
- course lesson map;
- visual course requirements.

### Stage 2 — Read-only app proof

Status: not started.

Goal:
Before any app changes, verify current `/opt/ai-starter-community` state:
- branch;
- HEAD;
- remote;
- git status;
- modules;
- routes;
- tests;
- service state;
- public checks.

### Stage 3 — App work

Status: blocked until Stage 1 and Stage 2 are complete.

Potential future work:
- landing continuation;
- materials section;
- course integration;
- payment design;
- AI-sales agent design.
- safety boundaries
- integration plan
