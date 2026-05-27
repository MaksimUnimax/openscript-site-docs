# AGENTS.md — OpenScript Site Docs Codex Contract

This repository is a documentation/source-of-truth repo for the main OpenScript / AI Starter Community website.

It is not the application source repo.
It is not OpenScript Agent Lab.
It is not APM.
It is not OpenDesign Lab.
It is not a runtime repo.

## Main product

The main product is the OpenScript / AI Starter Community website:

- public landing;
- user registration;
- email verification;
- login/logout;
- password reset;
- personal cabinet;
- “Работа с ИИ” materials section;
- tariffs;
- paid options;
- admin;
- email notifications;
- future payments;
- future AI-sales agent;
- course/materials after payment inside cabinet.

Courses are part of the main site materials area, not a separate main project.

## Mandatory behavior

- Follow the user task exactly.
- One run = one task.
- Do not make broad unrelated changes.
- Do not guess.
- If facts are missing, STOP and report what is missing.
- Do not read or print secrets.
- Do not touch runtime directories.
- Do not touch application repos unless the prompt explicitly asks for read-only inventory.
- Do not modify live services.
- Do not modify nginx, systemd, environment files, databases, logs, state, tmp, venv, cache, or auth files.
- Do not include tokens, passwords, cookies, private keys, reset links, or credentials in commits or reports.
- Do not assume ChatGPT attachments are available on the server.
- Use only exact documents listed in `DOCS_TO_READ`.
- Do not read the entire repository unless the task explicitly asks for repository inventory.

## Documentation model

The source-of-truth path is:

`docs/codex_source/`

The main entrypoint is:

`docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`

The index is:

`docs/codex_source/index.yaml`

Project docs, app docs, landing docs, materials/course docs, workflow docs, server docs and tool/vendor docs are intentionally separated.

If a task depends on a tool/vendor contract and the relevant vendor documentation is missing or stub-only, STOP with:

`STOP_DOCS_MISSING`

## Reports

Every run must end with:

CHATGPT_REPORT_BEGIN
RESULT: SUCCESS / STOP / FAIL
TASK_TYPE:
WHAT_WAS_DONE:
FILES_CREATED_OR_CHANGED:
VALIDATION:
GIT:
RISKS:
WHAT_WAS_NOT_DONE:
NEXT_RECOMMENDED_STEP:
CHATGPT_REPORT_END

## Git rules

- Check `git status` before and after.
- Commit only scoped documentation changes.
- Do not commit generated junk, caches, logs, secrets, runtime files, or downloaded archives unless explicitly requested.
- If remote push is requested but remote is missing or auth is unavailable, keep local commit and report `STOP_REMOTE_NOT_READY`.

