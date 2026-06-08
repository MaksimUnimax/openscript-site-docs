# Current status

STATUS: INITIAL_FROM_CURRENT_REPO_DOCS

## CURRENT_STATUS_20260529_AI_STARTER_COMMUNITY

### Current active block

Repo documentation memory update for the main OpenScript / AI Starter Community site.

### Main project

OpenScript / AI Starter Community is the main product.

Main app repo:
`/opt/ai-starter-community`

Main site:
`https://openscript.ru`

Docs repo:
`/opt/openscript-site-docs`

Public docs repo:
`https://github.com/MaksimUnimax/openscript-site-docs`

### Current source-of-truth correction

Current docs repo may still contain legacy OpenScript Agent Lab framing. This is stale for the current docs task. The canonical active project for this repo must be OpenScript / AI Starter Community.

### App state known from recent reports

Recent successful app commits reported in dialogue include:
- `ae477f553a4292ad9511a48e8c27f2bcfc6bb5c3` — non-course pages aligned with landing theme.
- `604535cb68f4df9fb0bac318f92f939dd6931d18` — landing authenticated state fixed.
- `fe22dca270fcda5d2a4591835f5286f38c6fecba` — authenticated navigation and learning links fixed.
- `f8f14a24052e60e88103344a57b440eda8d2fc40` — course expanded to ten lessons.
- `acbabbe050c2a10b699a32e0f08ad956a1a1a88d` — cabinet settings and auth header identity added.
- `d51ae5f8e7156c4d2a498b463ac0abab38940e75` — learning block layout refined and server-side access tests reported.

These commits are application-repo facts from Codex reports and should not be reproduced as docs repo history.

### Current product rules

- User registers before payment.
- Courses/materials are in the learning/materials section, currently visible as “Обучение”.
- First successful payment in the future must permanently unlock materials.
- Current durable access mechanism is `materials_access_granted_at` / materials access helper.
- Admin access is always open.
- Payment model/success handler is not yet proven/implemented.
- Do not invent payment flow in docs or app tasks.
- Future payment success handler must set the existing durable materials access flag or canonical entitlement derived from it.

### Current cabinet/materials state

`/cabinet` includes:
- account identity in header;
- settings link;
- settings page with password change only;
- learning block above account block;
- two-column learning block:
  - “Обучение” with course entry;
  - “Обучающий проект” with protected file download;
- locked/unlocked state based on server-side access;
- locked state readable but not clickable.

### Current course state

Course has 10 lessons:
1. Как устроена работа с ИИ-разработкой
2. Начало работы с ChatGPT
3. Документация как контроль разработки
4. Обновление документации
5. Новый диалог через документы
6. Git: история, commit, push и откат
7. Как проходит рабочий run Codex
8. PowerShell, Terminal и подключение к серверу
9. Сервер, Codex, AGENTS.md и Skills
10. Ошибки, лайфхаки и правила работы

Course requirements:
- all visible labels in Russian;
- no free-form textarea practice;
- checks should be click-based tests with ready answers;
- ChatGPT prepares Codex prompts;
- user returns Codex report to ChatGPT;
- ChatGPT explains report in simple language;
- course should be visual, not text-only;
- selected lesson is preserved through query parameter, not hash;
- quiz progress counts answered questions, including wrong answers.

### Current stop-point

Docs repo must be refined before broad future app work. The next Codex run should remain docs-only unless the user explicitly switches back to app implementation.

## CURRENT_STATUS_20260604_COURSE_LESSON_SWAP_ACCEPTED

### Current active block

Docs repo memory update for the accepted app course lesson swap and Codex lesson rewrite.

### Accepted app course commit

- `daaa8fcd84d448b94c0f16b5302c90086251b9ac` — Swap course lessons 5 and 6.

### Current course state

Course has 9 lessons:
1. Как устроена работа с ИИ-разработкой
2. Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст
3. Git: история, commit, push и откат
4. Старт проекта: сначала документация, потом разработка
5. Codex, AGENTS.md, Skills, токены и роль модели
6. PowerShell, Terminal и подключение к серверу
7. Старт работы и рабочие run’ы Codex
8. Обновление документации и новый диалог
9. Частые ошибки и правила безопасной работы

### Current accepted scope

- Lesson 5 is now the Codex lesson.
- Lesson 5 scope: Codex as technical executor; ChatGPT manages development; Codex executes instructions; AGENTS.md; Skills; tokens; model choice; mini-model default for ordinary Codex runs; permissions; slash commands; server/workdir context; installation context; good vs bad Codex task; practice; quiz/check; pass criteria; common mistakes.
- Lesson 6 is now the Terminal/server lesson.
- Lesson 6 scope: Terminal; PowerShell; commands; server; SSH; safe commands; dangerous commands; secrets; practice; quiz/check; pass criteria; common mistakes.

### Current stop-point

Course lesson content change is accepted in the app repo.
Docs repo now records that accepted state.
Next safe step is either:
1. user visual review of lessons 5 and 6 on the course page; or
2. if visual review is accepted, choose the next docs/app task from the current product stop-point.

Do not start payment, production, Agent Lab, or broad app work automatically.

## CURRENT_STATUS_20260608_COURSE_LESSON_7_REWRITE_VERIFIED

### Current active block

Docs repo memory update for the verified current course state and legacy bridge reclassification.

### Verified source inspection

- `source/app/materials/course_content/drafts/dair_smoke_20260529/index.html`
- `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- `source/tests/test_course_rendering.py`

### Accepted app course commit

- `f6f5c2b100296efd69c67fa7387550cf2595340d` — Rewrite lesson 7 process workflow

### Current course state

Course has 9 lessons:
1. Как устроена работа с ИИ-разработкой
2. Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст
3. Git: история, commit, push и откат
4. Старт проекта: сначала документация, потом разработка
5. Codex, AGENTS.md, Skills, токены и роль модели
6. PowerShell, Terminal и подключение к серверу
7. Процесс работы
8. Обновление документации и новый диалог
9. Частые ошибки, лайфхаки и правила работы

### Current lesson 7 scope

- Lesson 7 title: `Процесс работы`.
- Lesson 7 explains `run`, `design run`, `fix run`, and `proof run`.
- Lesson 7 explains one-run/one-task control logic.
- Lesson 7 explains `context` and `context window`.
- Lesson 7 explains `prefix`-extension practice.
- Lesson 7 includes a starter prompt panel for `Prompt для создания расширения`.
- The starter prompt panel has `Смотреть prompt`, `Скопировать prompt`, `Скачать .md`, and a hidden readonly textarea.

### Current prompt panels found in the source

- Lesson 6: starter prompt for project documentation start.
- Lesson 7: starter prompt for prefix-extension practice.
- Lesson 8: starter prompt for docs update.
- Lesson 8: starter prompt for new dialogue.

### Legacy bridge reclassification

- `docs/codex_source/project/module_map.md`, `docs/codex_source/project/project_snapshot.md`, and `docs/codex_source/project/project_overview.md` are legacy/imported history, not current site memory.
- Current site module map: `docs/codex_source/module_map/module_map.md`.
- Current site status: `docs/codex_source/project/current_status.md` and `docs/codex_source/project/CURRENT_STATUS.md`.

### Current stop-point

The current app course baseline is verified and remains the accepted lesson 7 rewrite.
Next safe app step remains the proof-only design workflow preflight.
