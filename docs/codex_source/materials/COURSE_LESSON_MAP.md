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
