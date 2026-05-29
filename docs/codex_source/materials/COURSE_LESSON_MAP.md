# Course lesson map

## COURSE_LESSON_MAP_20260529_CURRENT_10_LESSONS

Current course structure:

1. **Как устроена работа с ИИ-разработкой**  
   Roles and high-level workflow: user, ChatGPT, Codex, reports and verification.

2. **Начало работы с ChatGPT**  
   Start project discussion with ChatGPT. ChatGPT acts as professional architect and leading programmer, clarifies goal, proposes architecture/stack/roadmap/TZ and prepares Codex tasks.

3. **Документация как контроль разработки**  
   Documentation is not just memory. It controls development against TZ and roadmap, prevents scope drift and supports evaluation of Codex results.

4. **Обновление документации**  
   When and how to update documentation after important decisions, rule changes, accepted results and status changes.

5. **Новый диалог через документы**  
   Starting a new ChatGPT dialogue safely through current docs, not memory. Use context/docs/prefix rules to prevent lost context.

6. **Git: история, commit, push и откат**  
   Git basics for project owners: repository, commit, push, diff, rollback and deploy key explanation for students.

7. **Как проходит рабочий run Codex**  
   One safe Codex run: proof, one task, checks, commit/push, report, ChatGPT review and user acceptance.

8. **PowerShell, Terminal и подключение к серверу**  
   Basic terminal/SSH commands, server connection, safe command handling, git/status/log commands.

9. **Сервер, Codex, AGENTS.md и Skills**  
   Server environment, Codex authorization, permissions, model choice, AGENTS.md rules, Skills.

10. **Ошибки, лайфхаки и правила работы**  
   Frequent mistakes and practices: rare testing, too-large runs, docs updates, tracking AI/tool news, open-source reuse, Chrome rule reminder extension, context window, not dialoguing with Codex.

### Course behavior requirements

- 10 lessons are visible in navigation.
- URL state supports `?lesson=lesson-1` through `?lesson=lesson-10`.
- No `location.hash`.
- No `scrollIntoView`.
- All visible labels in Russian.
- Quiz progress counts answered questions, not only correct answers.
- Wrong answer still counts as completed question.
- Course content must not include old “Сделай мне ИИ-агента” example unless explicitly reintroduced.
- No visible “Тестовая версия курса”.
- No textarea practice.
