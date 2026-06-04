# Roadmap

STATUS: INITIAL_FROM_CURRENT_REPO_DOCS

This file is append-only.

Do not rewrite historical blocks destructively.

## ROADMAP_UPDATE_20260529_SITE_LEARNING_AND_DOCS_STATE

### Completed / accepted stages

#### Stage 0 — docs repo bootstrap
Status: completed.

The docs repo `/opt/openscript-site-docs` exists and is pushed to:
`https://github.com/MaksimUnimax/openscript-site-docs`.

#### Stage 0.1 — GitHub remote / deploy key / push
Status: completed.

Deploy key/push setup was completed earlier. The deploy key teaching content belongs in the student Git lesson, not in workflow rules, unless a later explicit decision changes that.

#### Stage 0.2 — deploy key lesson block
Status: completed.

Deploy key explanation was added to the Git lesson context for students.

#### Stage 1 — main site UI alignment
Status: substantially completed / needs visual follow-up only.

Completed/reported:
- non-course pages aligned with the main landing style;
- authenticated home state fixed;
- shared authenticated navigation improved;
- `/cabinet` received account identity and settings;
- `/cabinet/settings` contains only password change;
- “Работа с ИИ” navigation label was changed to “Обучение” in current UI.

#### Stage 2 — course structure/content rewrite
Status: completed as current working baseline.

Course was restructured from 9 to 10 lessons:
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

#### Stage 3 — learning access gating
Status: implemented as application baseline, but future payment integration remains open.

Implemented/reported:
- learning block in `/cabinet` has locked/unlocked states;
- access uses durable `materials_access_granted_at` / materials access helper;
- admin access should always be open;
- unpaid users see readable locked content but no active hrefs;
- direct protected course/download routes are blocked server-side for unpaid users;
- student project file is served through protected backend route, not public static.

### Current active documentation stage

#### Stage 4 — documentation refinement
Status: active.

Goal:
Bring docs repo into a coherent source-of-truth for OpenScript / AI Starter Community.

Must refine:
- canonical TZ;
- roadmap;
- current status;
- decisions;
- module map;
- materials/course specs;
- learning access flow;
- auth/cabinet/settings flow;
- course lesson map;
- payment/open questions.

### Not next

Do not start these before docs refinement is updated:
- new app implementation;
- payment implementation;
- tariff implementation;
- course generator redesign;
- Agent Lab/APM/OpenDesign work;
- runtime/server changes.

### Correct next technical app block after docs update

After this docs update, if app work resumes, the next app task must be chosen from the current UI/product stop-point, not from stale docs. Current recent app-level open items include:
- final visual polish of learning block buttons/text alignment if not already accepted;
- full proof of admin/paid/unpaid learning access in live-equivalent tests;
- future payment success integration to set permanent materials access.

## ROADMAP_UPDATE_20260604_COURSE_LESSON_SWAP_ACCEPTED

### Completed / accepted stages

#### Stage 4.1 — course lesson 5/6 swap accepted
Status: completed.

Accepted app commit:
`daaa8fcd84d448b94c0f16b5302c90086251b9ac`

Current accepted course lesson map:
1. Как устроена работа с ИИ-разработкой
2. Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст
3. Git: история, commit, push и откат
4. Старт проекта: сначала документация, потом разработка
5. Codex, AGENTS.md, Skills, токены и роль модели
6. PowerShell, Terminal и подключение к серверу
7. Старт работы и рабочие run’ы Codex
8. Обновление документации и новый диалог
9. Частые ошибки и правила безопасной работы

Current stop-point:
The course lesson content change is accepted in the app repo. Docs repo now records that accepted state.
Next safe step is either visual review of lessons 5 and 6 on the course page or the next docs/app task from the current product stop-point.

### Not next

Do not start payment, production, Agent Lab, or broad app work automatically.
