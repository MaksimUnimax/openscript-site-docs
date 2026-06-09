# Current status

STATUS: INITIAL_FROM_CURRENT_REPO_DOCS

## CURRENT_STATUS_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION

### Current active block

Docs repo memory update for the verified live cabinet/account-blocks/paid-options iteration. Manual browser verification is still pending unless the user explicitly confirms acceptance.
Canonical detailed current status is `docs/codex_source/project/current_status.md`.

### Current live state summary

- Latest app commit for the current live cabinet/account-blocks/paid-options iteration: `7c94211819ddb334575d7835152637972930d393`
- Active block: `cabinet_account_blocks_paid_options_live_iteration`
- Paid-options cabinet block is live; real payment processing is still not implemented.
- Server-backed account blocks are live in `/cabinet`.
- Account actions use fetch-based no-jump handling and preserve scroll position.
- Account cards use bounded tracks and do not stretch full width on desktop/tablet when only one card is visible.
- Activation email is wired to the owner user's registered email.
- Real payment remains NOT_YET_PROVEN.
- Password-secret encryption policy remains open / not yet proven.
- Agent Lab content is legacy / no-touch and not the current site corpus.

### Current stop-point

Manual browser verification of the latest cabinet/account-blocks/paid-options behavior is still pending unless explicitly confirmed by the user.

## Historical / superseded context

The sections below are preserved append-only history from earlier site and course states.
They are not the current active block and must not be selected as the current stage when the 2026-06-09 cabinet/account-blocks/paid-options status exists above.

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

## CURRENT_STATUS_20260608_COURSE_ORDER_AND_FINAL_SECTION_REPAIR

### Current active block

Docs repo memory update for the verified current course state and legacy bridge reclassification.

### Verified source inspection

- `source/app/materials/course_content/drafts/dair_smoke_20260529/index.html`
- `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- `source/tests/test_course_rendering.py`

### Accepted app course commit

- `f6f5c2b100296efd69c67fa7387550cf2595340d` — Rewrite lesson 7 process workflow

### Current course state

Course has 9 numbered lessons plus a visible final section:
1. Как устроена работа с ИИ-разработкой
2. Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст
3. Git: история, commit, push и откат
4. Codex, AGENTS.md, Skills, токены и роль модели
5. PowerShell, Terminal и подключение к серверу
6. Старт проекта: сначала документация, потом разработка
7. Процесс работы
8. Обновление документации и новый диалог
9. Частые ошибки, лайфхаки и правила работы
10. Финал курса

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

The current app live state now includes the server-backed cabinet account blocks, moderator assignment, activation email wiring, paid-options cabinet block, no-jump account action handling, and bounded account card width.
Next safe step is manual browser verification of the live cabinet/account-blocks/paid-options behavior, unless the user explicitly confirms acceptance.

## CURRENT_STATUS_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION

### Current active block

Docs repo memory update for the verified live cabinet/account-blocks/paid-options iteration. Manual browser verification is still pending unless the user explicitly confirms acceptance.

### Current live state

- Paid-options cabinet block is live and shows active add-ons from the database.
- The base AI / GPT tool option is hidden from the add-on activation block.
- Add-ons are ordered by price descending.
- The buy button remains a safe placeholder; real payment processing is still not implemented.
- Server-backed account blocks are live in `/cabinet`.
- LocalStorage is no longer the source of truth for account blocks.
- ChatGPT, Сервер, and Почта are supported block types.
- Owner is resolved server-side and hidden from the visible UI.
- Manual title and email inputs were removed from the account block UI.
- Admin and moderator can create, edit, delete, and activate account blocks.
- Moderator does not gain full admin dashboard rights.
- Activation email is wired to the owner user's registered email.
- Activation text uses elapsed-day wording, not remaining-days wording.
- Account actions use fetch-based no-jump handling and preserve scroll position.
- Account cards use bounded tracks and do not stretch full width on desktop/tablet when only one card is visible.
- Production test-user cleanup was completed with a backup before deletion.

### Accepted live-source commits

- `f10fb8efd2b2d044f66122952675ee66cc0dbd3d` — paid-options hide-base/sort/alignment live deploy
- `3e45d12c1807eae877065459a5c68f762ef02da1` — account_blocks backend/service foundation
- `a16ab80cf354ddfe1a3b48e3d5ee52e716c9b00c` — server-backed cabinet UI and admin/moderator management
- `f67ef013eb831ec76ce3cf69eca40fc8da19d0a8` — moderator assignment for users.role
- `da3ce7f939bffe1cbb802048964c83aae96214a9` — compact card UI and elapsed activation status
- `1a89fd5eea26e955b4f2fe33cfb6e13cf44f3201` — owner selector / action form fixes
- `a3bd97243a267691c6d06403223a470c2fafdefb` — activation email import-cycle/runtime fix
- `7c94211819ddb334575d7835152637972930d393` — no-jump account actions and bounded account card width

### Manual verification status

- Manual browser verification of the latest no-jump/card-width/account-email behavior is still pending unless explicitly confirmed by the user.
- This docs update records the technical deployed state only.
- Real payment processing remains NOT_YET_PROVEN.
