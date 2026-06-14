# Course lesson map

## COURSE_LESSON_MAP_20260601_CURRENT_9_LESSONS

Текущая структура курса:

1. **Как устроена работа с ИИ-разработкой**
   Роли и общая схема работы: пользователь описывает цель, ChatGPT помогает превратить её в технически понятную задачу, Codex выполняет конкретный шаг, а результат принимается только после проверки.

2. **Документы проекта: ТЗ, roadmap, правила и контекст**
   Ученик понимает, какие документы нужны проекту, зачем они контролируют работу и почему без них нельзя безопасно отдавать задачи Codex.

3. **Git: история, commit, push и откат**
   Git на уровне владельца проекта: репозиторий, история изменений, commit, push, diff, откат и понимание отчёта Codex по Git.

4. **Старт проекта: подготовка документов с ChatGPT и push в Git**
   Ученик начинает реальную работу: вместе с ChatGPT готовит документы проекта и отправляет их в Git. После этого у ученика есть готовая основа для дальнейшей работы.

5. **PowerShell, Terminal и подключение к серверу**
   Базовые команды терминала и SSH, подключение к серверу, безопасное выполнение команд, git status/log/diff.

6. **Сервер, Codex, AGENTS.md и Skills**
   Серверная среда, авторизация Codex, permissions, выбор модели, AGENTS.md и Skills.

7. **Старт работы и рабочие run’ы Codex**
   Один безопасный run Codex: одна задача, понятные границы, проверки, commit/push, отчёт, проверка ChatGPT и приёмка пользователем.

8. **Обновление документации и новый диалог**
   Когда и как обновлять документацию после важных решений, изменения правил, принятого результата и изменения статуса. Как безопасно начинать новый диалог через актуальные документы, а не по памяти.

9. **Частые ошибки, лайфхаки и правила работы**
   Частые ошибки и практики: редкая проверка результата, слишком большие runs, забытое обновление документации, новости ИИ-инструментов, готовые open-source решения, расширение для напоминания правил, контекстное окно и запрет длинного диалога с Codex.

### Требования к поведению курса

- В навигации видно 9 уроков.
- URL/ID поддерживает `lesson-1` ... `lesson-9`.
- Не должно быть видимого урока 10.
- Старый отдельный урок “Новый диалог через документы” не должен быть отдельной карточкой; его тема входит в урок 8.
- Не использовать `location.hash`.
- Не использовать `scrollIntoView`.
- Все видимые labels на русском.
- Прогресс теста считается по отвеченным вопросам, а не только по правильным ответам.
- Неправильный ответ тоже засчитывается как выполненный вопрос.
- В курсе не должно быть старого примера “Сделай мне ИИ-агента”, если он явно не возвращён отдельным решением.
- Не должно быть видимого текста “Тестовая версия курса”.
- Не должно быть textarea-практики.

## COURSE_LESSON_MAP_20260603_SEMANTIC_BLOCKS_ACCEPTED

### Current visible lesson map

1. **Как устроена работа с ИИ-разработкой**
   ChatGPT, Codex, roles, overall workflow, beginner-level meaning framing.

2. **Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст**
   Minimum document set for the project, why docs preserve context and control work.

3. **Git: история, commit, push и откат**
   Git/GitHub at owner level, commit, push, diff, rollback, proof-by-facts.

4. **Старт проекта: сначала документация, потом разработка**
   Start project through ChatGPT documentation, optional starter prompt, repo docs created by Codex from prompt text, deploy-key flow.

5. **PowerShell, Terminal и подключение к серверу**
   PowerShell/Terminal, server, SSH, safe commands, secrets.

6. **Codex, AGENTS.md и Skills**
   Technical task boundaries, AGENTS.md, Skills, exact task execution.

7. **Старт работы и рабочие run’ы Codex**
   One Codex run = one task; checks, report, SUCCESS/STOP/FAIL.

8. **Обновление документации и новый диалог**
   Docs update, stop-point, current context, start new dialogue safely.

9. **Частые ошибки и правила безопасной работы**
   Common mistakes, proof, docs, Git, secrets, and safe workflow rules.

### Current implementation facts

- Lessons 1–9 are split into semantic blocks/cards in `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`.
- The lesson renderer supports `section.blocks` with fallback to old `contentHtml`.
- Lesson 4 keeps the starter prompt controls:
  - Перейти к стартовому prompt
  - Смотреть prompt
  - Скопировать prompt
  - Скачать .md
- Lesson 4 deploy-key logic is corrected: private key stays on the server and is used locally by Codex; user adds only the public key to GitHub Deploy keys and returns confirmation only.
- The latest accepted app commit for this course work is `a5a2f6ef40338959a659bc9feecf0a23c46a0c70`.

## COURSE_LESSON_MAP_20260604_LESSON_5_6_SWAP_ACCEPTED

### Current visible lesson map

1. **Как устроена работа с ИИ-разработкой**
   ChatGPT, Codex, roles, overall workflow, beginner-level meaning framing.

2. **Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст**
   Minimum document set for the project, why docs preserve context and control work.

3. **Git: история, commit, push и откат**
   Git/GitHub at owner level, commit, push, diff, rollback, proof-by-facts.

4. **Старт проекта: сначала документация, потом разработка**
   Start project through ChatGPT documentation, optional starter prompt, repo docs created by Codex from prompt text, deploy-key flow.

5. **Codex, AGENTS.md, Skills, токены и роль модели**
   Codex as technical executor; ChatGPT manages development; Codex executes instructions; AGENTS.md; Skills; tokens; model choice; mini-model default for ordinary Codex runs; permissions; slash commands; server/workdir context; installation context; good vs bad Codex task examples; practice; quiz/check; pass criteria; common mistakes.

6. **PowerShell, Terminal и подключение к серверу**
   Terminal, PowerShell, commands, server, SSH, safe commands, dangerous commands, secrets, practice, quiz/check, pass criteria, common mistakes.

7. **Старт работы и рабочие run’ы Codex**
   One Codex run = one task; checks, report, SUCCESS/STOP/FAIL.

8. **Обновление документации и новый диалог**
   Docs update, stop-point, current context, start new dialogue safely.

9. **Частые ошибки и правила безопасной работы**
   Common mistakes, proof, docs, Git, secrets, and safe workflow rules.

### Accepted app course commit

- `daaa8fcd84d448b94c0f16b5302c90086251b9ac` — latest accepted app course commit after swapping lessons 5 and 6 and rewriting the Codex lesson.

### Current lesson 5 scope

`Codex, AGENTS.md, Skills, токены и роль модели` now teaches:
- what Codex is;
- ChatGPT manages development, Codex executes instructions;
- where Codex works;
- AGENTS.md;
- Skills;
- tokens;
- why not to chat freely with Codex;
- model choice and mini-model default for ordinary Codex runs;
- permissions;
- slash commands;
- installation/server context;
- good vs bad Codex task examples;
- practice;
- quiz/check;
- pass criteria;
- common mistakes.

### Current lesson 6 scope

`PowerShell, Terminal и подключение к серверу` now teaches:
- Terminal;
- PowerShell;
- commands;
- server;
- SSH;
- safe commands;
- dangerous commands;
- secrets;
- practice;
- quiz/check;
- pass criteria;
- common mistakes.

## COURSE_LESSON_MAP_20260608_CURRENT_9_LESSONS_AND_PROMPT_PANELS_VERIFIED

### Current visible lesson map

This current block supersedes the older 2026-06-04 swap block and the stale no-final-section wording.

1. **Как устроена работа с ИИ-разработкой**
   ChatGPT, Codex, roles, overall workflow, beginner-level meaning framing.

2. **Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст**
   Minimum document set for the project, why docs preserve context and control work.

3. **Git: история, commit, push и откат**
   Git/GitHub at owner level, commit, push, diff, rollback, proof-by-facts.

4. **Codex, AGENTS.md, Skills, токены и роль модели**
   Codex as technical executor; ChatGPT manages development; Codex executes instructions; AGENTS.md; Skills; tokens; model choice; mini-model default for ordinary Codex runs; permissions; slash commands; server/workdir context; installation context; good vs bad Codex task examples; practice; quiz/check; pass criteria; common mistakes.

5. **PowerShell, Terminal и подключение к серверу**
   Terminal, PowerShell, commands, server, SSH, safe commands, dangerous commands, secrets, practice, quiz/check, pass criteria, common mistakes.

6. **Старт проекта: сначала документация, потом разработка**
   Start project through ChatGPT documentation, starter prompt, repo docs created by Codex from prompt text, deploy-key flow.

7. **Процесс работы**
   One run per task, run types, context window, prefix-extension practice, starter prompt panel with read-only prompt preview and actions.

8. **Обновление документации и новый диалог**
   Docs update, stop-point, current context, start new dialogue safely.

9. **Частые ошибки, лайфхаки и правила работы**
   Common mistakes, proof, docs, Git, secrets, and safe workflow rules.

10. **Финал курса**
   Visible final section with course wrap-up, next steps, and closing guidance.

### Current source facts

- The rendered course navigation shows 9 numbered lessons and the course source includes a visible final section (`lesson-10`).
- Lesson 7 title is `Процесс работы`.
- Lesson 7 includes a starter prompt panel with `Смотреть prompt`, `Скопировать prompt`, `Скачать .md`, and a readonly textarea preview.
- Current prompt panels found in the source:
  - lesson 6 starter prompt for project documentation start;
  - lesson 7 starter prompt for prefix-extension practice;
  - lesson 8 starter prompt for docs update;
  - lesson 8 starter prompt for new dialogue.

## COURSE_LESSON_MAP_SITE_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION

### Current visible lesson map

The course still presents 9 numbered lessons plus a visible final section.

### Current materials state

- Lesson 3 Git now uses a real screenshot carousel from static assets.
- The Git carousel screenshots are served from `/static/course-assets/dair-smoke-20260529/git-carousel/`.
- Slide sizing, labels, and the first slide label were polished in the current course memory.
- Placeholder carousels are used for the remaining practical lessons.
- Lesson 6 project-start had been missed in the first pass and was fixed with a placeholder carousel.
- Lesson 7 prefix-extension keeps a placeholder carousel pattern.
- Lesson 8 docs update / new-dialog workflow uses the same placeholder carousel pattern when present in source.
- Carousel controls are scoped per carousel instance, not shared globally.
- The course remains beginner-facing and click-based.

### Reported app/source facts tied to this memory update

- `2ab492d03a472f26a95d836799c132ca35b5e1c1` — Serve Git carousel screenshots from static assets
- `91a849344708a3629bfb2be2862e78a9cd02c81c` — Polish Git carousel screenshot sizing and labels
- `4755532dcf186d653f132f1e79d43b11f264a4ea` — Restore Git lesson term emphasis and step one label
- `56aac56f3eb30f703b86d82fa40e7e33b27cd7de` — Add placeholder carousels to practical lessons
- `b1e208c4f13f7651772062cb22aaaf6421d4540a` — Add lesson 6 practice carousel
- `3e8e351564b07c154a887e768b1c37711ffb2634` — Restore account grid and make VPN a real block type
- `fbb1477a69ee517ff30736326617e5d4b914b320` — Polish VPN panel and account card titles; if this commit is only in a feature/live-synced branch, treat it as pending branch integration until fast-forwarded

### Not current

- Real payment remains NOT_YET_PROVEN.
- Password-secret policy remains open.
- The separate collapsible VPN block request is pending/not proven.
- Agent Lab remains legacy history only.

## COURSE_LESSON_MAP_20260614_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED

### Current visible lesson map

The course still presents 9 numbered lessons plus a visible final section.

1. **Как устроена работа с ИИ-разработкой**
   ChatGPT, Codex, roles, overall workflow, beginner-level meaning framing.

2. **Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст**
   Minimum document set for the project, why docs preserve context and control work.

3. **Git: история, commit, push и откат**
   Git/GitHub at owner level, commit, push, diff, rollback, proof-by-facts.

4. **Codex, AGENTS.md, токены и роль модели**
   Codex as technical executor; ChatGPT manages development; approved `рабочий шаг (run)` terminology; `лимиты ресурсов`; permissions; slash commands; run-types and common mistakes.

5. **PowerShell, Terminal и подключение к серверу**
   Terminal, PowerShell, commands, server, SSH, safe commands, dangerous commands, secrets, practice, quiz/check, pass criteria, common mistakes.

6. **Старт проекта: сначала документация, потом разработка**
   Start project through ChatGPT documentation, starter prompt, repo docs created by Codex from prompt text, deploy-key flow.

7. **Процесс работы**
   One run per task, run types, context window, prefix-extension practice, starter prompt panel with read-only prompt preview and actions.

8. **Обновление документации и новый диалог**
   Docs update, stop-point, current context, start new dialogue safely.

9. **Частые ошибки, лайфхаки и правила работы**
   Common mistakes, proof, docs, Git, secrets, and safe workflow rules.

10. **Финал курса**
   Visible final section with course wrap-up, next steps, and closing guidance.

### Accepted current facts

- Lesson 4 visible content no longer shows `Skills`, `Skill`, `/skills`, `plugins`, `plugin`, or `/plugins`.
- Lesson 4 uses approved `рабочий шаг (run)` terminology and clarifies `лимиты ресурсов`.
- Lesson 4 slash-command section now teaches only `/status`, `/model`, and `/permissions`, with the slash-menu explanation.
- Lesson 5 links `личный кабинет курса` and grammatical variants to `https://openscript.ru/cabinet` with `target="_blank"` and `rel="noreferrer"`.
- Lesson 6 includes the starter prompt panel for project documentation start.
- Lesson 8 includes starter prompt panels for docs update and new dialogue.
- Admin course export includes the three prompt markdown files.
