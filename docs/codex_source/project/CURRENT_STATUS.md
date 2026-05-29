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
