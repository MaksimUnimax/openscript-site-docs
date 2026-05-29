# Decisions

STATUS: INITIAL_FROM_CURRENT_REPO_DOCS

## DECISIONS_UPDATE_20260529_AI_STARTER_COMMUNITY

### DECISION_20260529_01 — Docs repo project identity

Decision:
The docs repo `openscript-site-docs` documents the main OpenScript / AI Starter Community site, not OpenScript Agent Lab.

Reason:
Public docs still contain legacy Agent Lab framing. Future runs must not confuse the projects.

Consequence:
All new docs updates must frame OpenScript / AI Starter Community as the active project. Legacy Agent Lab content may remain as history only until explicitly cleaned.

### DECISION_20260529_02 — Course is not root product

Decision:
The course/materials area is part of the main site learning/materials flow, not a standalone root product.

Current visible UI label:
“Обучение”.

Conceptual course/product topic:
“Работа с ИИ” / ChatGPT + Codex workflow.

Consequence:
Roadmap, TZ and module map must place course functionality under materials/learning, not as the whole product.

### DECISION_20260529_03 — Learning access source

Decision:
Until a real payment success path is implemented, learning/materials access must use existing durable access state:
`users.materials_access_granted_at` / materials access helper.

Admin access:
Always open.

Paid access:
A user with durable materials access gets course/download access.

Unpaid access:
Readable locked UI, no active hrefs, server-side route blocking.

Consequence:
Do not invent fake payment model, hardcoded email, query flag, localStorage flag, or frontend-only access.

### DECISION_20260529_04 — Future payment integration

Decision:
Future payment success must grant permanent learning/materials access by setting the existing durable access flag or the canonical entitlement derived from it.

Consequence:
Payment implementation must not create a duplicate access model.

### DECISION_20260529_05 — Protected student project file

Decision:
The “Обучающий проект” file must not be served from public static and must not expose a raw GitHub URL in rendered HTML.

Source:
`MaksimUnimax/openscript-agent-lab-student-kit/main/chatgpt/02_СТАРТ_ПРОЕКТА_GIT_ДОКУМЕНТАЦИЯ_СТРУКТУРА.md`

Consequence:
App stores a private copy and serves it through a protected backend route.

### DECISION_20260529_06 — Settings scope

Decision:
Cabinet settings currently contain only password change.

Consequence:
Do not add avatar/profile/tariff/notification/settings placeholders until explicitly requested.

### DECISION_20260529_07 — Course method

Decision:
Course checks should be interactive click tests with ready answers, not free-form text practice.

Consequence:
Do not reintroduce textarea practice unless explicitly requested.

### DECISION_20260529_08 — ChatGPT/Codex division in course

Decision:
The course must teach that ChatGPT is the professional technical specialist: architect, programmer, planner and prompt author. Codex is the server-side executor of a concrete technical task.

Consequence:
Do not tell the student that they must independently design architecture, stack, roadmap or Codex prompts before ChatGPT helps.
