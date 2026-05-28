# Context

## Origin

The user wants OpenScript to become a product that helps people without programming experience start making useful software with AI tools.

The current focus is the main website:
- landing;
- user flow;
- cabinet;
- paid materials;
- admin;
- future payment;
- future AI-sales agent.

## Important clarification

The course is not the main project.

The main project is the OpenScript / AI Starter Community website.

The course is part of the materials area:
- available after payment;
- located inside the cabinet/materials section;
- teaches the working method with ChatGPT and Codex.

## Working method

The workflow used in development must also be part of the product philosophy:

User -> ChatGPT -> Codex -> report -> ChatGPT explanation -> user visual check -> documentation update -> next step

## User corrections already accepted

- Do not treat the course as a separate root product.
- Main docs repo must describe the main website.
- Courses live inside the cabinet after payment.
- Rules and AGENTS.md are required.
- Codex must receive exact DOCS_TO_READ.
- Agent Lab and APM must not be touched.

## Context update 2026-05-28 — Main site docs repo is now the project memory

The project now has a dedicated source-of-truth documentation repo for the main OpenScript / AI Starter Community website.

The current canonical docs repo is:

- local: `/opt/openscript-site-docs`
- public: `https://github.com/MaksimUnimax/openscript-site-docs`

This docs repo is for the main website and cabinet product. It must not drift into a standalone course-only project.

The main product remains:

- public landing;
- registration;
- email verification;
- login/logout;
- password reset;
- user cabinet;
- “Работа с ИИ” materials area;
- courses inside materials after payment;
- tariffs;
- paid options;
- admin;
- email notifications;
- future payments;
- future AI-sales agent.

The course “Как разрабатывать с помощью ChatGPT и Codex” is part of the materials area, not the root project.

A deploy-key access pattern was tested during repo setup. For student-facing explanation, it belongs in the Git lesson. It was added to Lesson 7 in `COURSE_LESSON_MAP.md`. It must not be moved into `AGENTS.md` or workflow rules unless there is a future explicit decision.

The next safe phase is documentation refinement. The docs must be made strong enough so future ChatGPT/Codex work starts from repo memory, not from chat memory.

Before any future app work, Codex must perform read-only proof of `/opt/ai-starter-community`.
