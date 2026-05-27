# Continue After Break

When a dialogue is interrupted or a new chat starts:

1. Read `ENTRYPOINT_FOR_CHATGPT.md`.
2. Read `index.yaml`.
3. Read `CURRENT_STATUS.md`.
4. Read `CONTEXT.md`.
5. Read only task-specific docs.
6. Ask for or inspect the latest Codex report if needed.
7. Do not continue implementation until context is restored.

Safe user message template:

“Изучи документы проекта и сначала скажи:
что это за проект,
что уже сделано,
что сейчас главный этап,
какой следующий безопасный шаг.
Код пока не трогать.”

