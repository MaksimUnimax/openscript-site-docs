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

## D007 — Docs repo is active project memory

Decision:
`/opt/openscript-site-docs` and `https://github.com/MaksimUnimax/openscript-site-docs` are now the source-of-truth documentation repo for the main OpenScript / AI Starter Community website.

Reason:
The main app repo did not contain sufficient canonical documentation. Future work must not depend only on chat memory.

## D008 — Main site remains the root product

Decision:
The root product is the OpenScript / AI Starter Community website, not the course.

Reason:
The course exists inside “Работа с ИИ” after payment and supports the main product.

## D009 — Deploy-key explanation belongs in the Git lesson

Decision:
The deploy-key method is student-facing course content and belongs in Lesson 7 “Git простыми словами”.

Reason:
Students need to understand the safe pattern for giving Codex/GitHub write access to one repo. It is not a ChatGPT/Codex workflow rule for this docs repo.

## D010 — No app work before read-only proof

Decision:
Before any future implementation in `/opt/ai-starter-community`, run a read-only proof of the app repo.

Reason:
The docs repo now exists, but the app state must be verified before live app changes.

## D011 — Stage 1 is docs refinement

Decision:
The next project phase is not app work. It is refinement of the documentation package.

Reason:
The current docs are initial/stub and must be strengthened before they can reliably guide implementation.
