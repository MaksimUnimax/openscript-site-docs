# OpenScript Site Docs

This repository is the source-of-truth documentation pack for the main OpenScript / AI Starter Community website.

Main site:

**https://openscript.ru**

Main application repo:

`/opt/ai-starter-community`

This documentation describes:

- public landing;
- registration and authentication;
- email verification and password reset;
- personal cabinet;
- “Работа с ИИ” materials section;
- tariffs;
- paid options;
- admin;
- email notifications;
- future payment flow;
- future AI-sales agent;
- future courses/materials inside the paid user area.

This is documentation only.

It must not contain:

- secrets;
- runtime files;
- database dumps;
- logs;
- .env values;
- auth tokens;
- private keys;
- Codex auth files;
- generated backups from live app repos.

The intended workflow:

1. ChatGPT reads `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`.
2. ChatGPT reads `docs/codex_source/index.yaml`.
3. For each task, ChatGPT gives Codex exact `DOCS_TO_READ`.
4. Codex reads only the exact documents needed for one task.
5. One Codex run equals one task.
6. Codex reports with `CHATGPT_REPORT_BEGIN` / `CHATGPT_REPORT_END`.
7. ChatGPT explains the report to the user in simple language.
8. Documentation is updated after important decisions or run results.

