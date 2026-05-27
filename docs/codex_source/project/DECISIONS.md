# Decisions

## D001 — Main product is the site

Decision:
The main product is OpenScript / AI Starter Community website.

Not a standalone course repo.

## D002 — Courses are inside materials

Decision:
Courses/materials are inside “Работа с ИИ” in the personal cabinet after payment.

## D003 — Separate docs repo

Decision:
Create a separate docs/source-of-truth repo at `/opt/openscript-site-docs`.

Reason:
The main app repo currently lacks structured documentation.

## D004 — Root AGENTS.md is required

Decision:
Root `AGENTS.md` must exist.

Reason:
Codex needs a persistent contract for safe work.

## D005 — Exact DOCS_TO_READ

Decision:
Codex must receive exact task-specific `DOCS_TO_READ`.

Reason:
Reading all docs causes drift and wasted context.

## D006 — No unrelated repos

Decision:
Do not touch Agent Lab, APM, or OpenDesign Lab.

Reason:
They exist on the server but are not part of this current task.

