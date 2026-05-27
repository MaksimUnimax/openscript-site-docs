# ENTRYPOINT FOR CHATGPT

STATUS: initial

This is the first file ChatGPT must read at the start of a new project dialogue for the OpenScript / AI Starter Community website documentation project.

Purpose:

- prevent guessing from old chat memory;
- restore project context from repository documents;
- separate project docs from vendor/tool docs;
- force exact `DOCS_TO_READ` for Codex;
- keep ChatGPT as the project lead and Codex as the technical executor.

Do not rely on memory before reading this entrypoint.

## Current project

Project name:

**OpenScript / AI Starter Community**

Main site:

**https://openscript.ru**

Main app repo:

`/opt/ai-starter-community`

## Main product

The product is a website and personal cabinet for people without programming experience who want to start making simple programs, bots, scripts, automations and MVPs with AI tools.

Core product parts:

- landing;
- registration;
- cabinet;
- payment access model;
- “Работа с ИИ” materials;
- courses after payment;
- paid options;
- admin;
- future AI-sales agent.

## Main read path

1. `docs/codex_source/index.yaml`
2. `docs/codex_source/project/PROJECT_OVERVIEW.md`
3. `docs/codex_source/project/CURRENT_STATUS.md`
4. `docs/codex_source/workflow/RULES.md`
5. task-specific documents only

## Canonical rule

Codex must not be told to “read all docs”.
Codex must receive a short exact `DOCS_TO_READ` list for the current one task.

## Do not mix projects

Do not mix this project with:
- OpenScript Agent Lab / agent farm;
- APM / autopostmanager;
- OpenDesign Lab.

Those can be references only if a task explicitly says so.

