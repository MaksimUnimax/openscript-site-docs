# Context

STATUS: INITIAL_FROM_CURRENT_REPO_DOCS

This directory stores append-only dialogue context for ChatGPT and Codex.

Rules:
- never rewrite historical blocks destructively
- only append new blocks
- keep the manifest updated
- Codex should read the manifest and the tail, not the whole file, for future append work

## CONTEXT_UPDATE_20260529_AI_STARTER_COMMUNITY_SITE_CURRENT_STATE

Project: OpenScript / AI Starter Community.

Main site: https://openscript.ru  
Main application repo on server: `/opt/ai-starter-community`  
Documentation repo on server: `/opt/openscript-site-docs`  
Public docs repo: `https://github.com/MaksimUnimax/openscript-site-docs`

### Active project identity

The active project for this docs repo is the main OpenScript / AI Starter Community site, not OpenScript Agent Lab, APM, OpenDesign, or a standalone course repository.

The course/materials area is a product section inside the main site. It must not become the root product in documentation or roadmap.

### Current product framing

OpenScript helps a non-programmer start a first AI-assisted development project. The user does not manually write application code. The workflow taught by the product is:

1. User describes the goal.
2. ChatGPT discusses the project, asks questions, acts as a professional technical specialist, designs the architecture/stack/roadmap/TZ and prepares Codex tasks.
3. Codex performs one concrete technical step on the server/repository and returns a report.
4. ChatGPT explains/verifies the report.
5. User checks the product result and accepts or rejects the step.
6. Important decisions are saved in project documentation.

### Learning/materials section

The paid learning/materials section is currently visible in the UI as “Обучение”. It contains:
- the course “Работа с ИИ” / “Как разрабатывать с помощью ChatGPT и Codex”;
- a protected downloadable “Обучающий проект” student file;
- learning access gated server-side.

Earlier documents may call this area “Работа с ИИ”. Current UI navigation uses “Обучение”. Documentation should treat these as the same learning/materials product area, with “Обучение” as the current visible UI label.

### Access model for learning/materials

Current application facts from dialogue/Codex reports:
- There is no proven payment transaction/order/subscription model yet.
- There is no proven payment success handler yet.
- The app already has durable user access state: `users.materials_access_granted_at`.
- The app has an access helper around `user_can_access_materials(...)` / materials access.
- The current learning gate must use this existing durable flag.
- Admin access must be always open.
- A normal user with `materials_access_granted_at` has access.
- A normal user without this flag has no access.

Future payment implementation must not invent a second access model. When payment is implemented, the successful payment path must grant permanent learning/materials access by setting the existing durable access flag or the canonical entitlement layer derived from it.

### Current protected learning resources

The learning block in `/cabinet` is a two-column block:
- left column: course entry “Обучение” with “Перейти к обучению”;
- right column: “Обучающий проект” with “Скачать файл”;
- bottom instruction text: “Пройдите обучение, затем скачайте файл, вставьте в чат ChatGPT и следуйте его инструкциям.”

The downloadable student project file source is the public GitHub student kit file:
`MaksimUnimax/openscript-agent-lab-student-kit/main/chatgpt/02_СТАРТ_ПРОЕКТА_GIT_ДОКУМЕНТАЦИЯ_СТРУКТУРА.md`

The app must not expose the GitHub raw URL in rendered HTML. The file must be copied into private app-owned storage and served only through a protected backend route.

### Server-side protection requirement

Frontend disabled buttons are not enough.

For unpaid non-admin users:
- `/cabinet` may show readable locked learning content;
- rendered locked HTML must not contain hrefs to the course or file download;
- direct course URL must be blocked server-side;
- direct course data/assets route must be blocked if it exposes protected course content;
- direct download route must be blocked server-side;
- devtools HTML changes must not bypass access.

For admin users:
- access is always open;
- course link and download link must be active;
- course route and download route must allow access.

For paid/materials-access users:
- course link and download link must be active;
- course route and download route must allow access.

### Current UI/documented implementation status from dialogue

Confirmed implemented/reported app changes include:
- non-course pages aligned to the main landing visual style;
- authenticated landing page no longer shows “Войти” or “Начать первый проект”;
- authenticated navigation uses “Обучение” and “Личный кабинет”;
- `/cabinet` header includes account identity and settings;
- settings page currently contains only password change;
- `/cabinet` learning block moved above account block;
- course expanded to 10 lessons;
- English service labels in course UI were removed/replaced with Russian labels;
- selected lesson is preserved through a `?lesson=lesson-N` query parameter, not hash navigation;
- course quiz progress counts answered questions, including wrong answers;
- course access and project file download are protected by server-side access gate;
- admin access must be consistent across header, cabinet learning block, course route and download route.

### Current caution

Some docs in this repo may still contain OpenScript Agent Lab content. That history must not be deleted blindly, but the canonical current project context for this docs repo must be corrected to OpenScript / AI Starter Community.
