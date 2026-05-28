# AGENTS.md - OpenScript Site Docs Contract

This repository is the documentation source-of-truth for the OpenScript / AI Starter Community website.

It is not the app repo, not runtime, and not a place for live service changes.

Core rules:
- One run = one task.
- Use exact docs only.
- Do not guess when docs or source do not prove behavior.
- Do not read or print secrets, tokens, private keys, cookies, passwords, or auth files.
- Do not touch runtime state, services, nginx, or systemd.
- Do not edit the app repo unless the task explicitly allows app work.
- Do not mix in unrelated repos or projects.
- If a task is a docs repair/import run, missing docs should be created or imported instead of stopping.

Current repo focus:
- OpenScript / AI Starter Community website docs
- Courses live inside the "Работа с ИИ" materials area in the main cabinet
- Tooling and vendor references belong under `docs/codex_source/tools/**`
- Project, materials, and workflow docs belong under `docs/codex_source/project/**`, `docs/codex_source/materials/**`, and `docs/codex_source/workflow/**`

Start here:
- `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`
- `docs/codex_source/index.yaml`

If a task prompt conflicts with this contract, follow the task prompt and report the conflict.
