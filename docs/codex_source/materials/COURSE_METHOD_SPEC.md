# Course method spec

## COURSE_METHOD_SPEC_UPDATE_20260529_CHATGPT_CODEX_COURSE

### Method

The course teaches the user how to work on projects with ChatGPT and Codex without manually writing code.

The user should learn:
- how to describe a goal;
- how to discuss and refine a project with ChatGPT;
- how ChatGPT creates technical documentation, roadmap and Codex prompts;
- how Codex executes one technical step;
- how to return Codex report to ChatGPT;
- how to check result by facts;
- how to update documentation and continue safely.

### Role framing

ChatGPT:
- AI assistant for dialogue, analysis and planning;
- in this course used as professional technical specialist;
- architect, programmer, planning lead and Codex prompt author;
- prepares architecture, stack, roadmap, TZ and exact Codex tasks.

Codex:
- AI coding agent/executor;
- works with project files, checks and reports;
- does not define the business goal;
- should not be used for long dialogue;
- receives one concrete technical task.

User:
- owner of goal and result;
- describes desired result;
- answers clarifying questions;
- checks result and accepts/rejects;
- does not need to know programming, architecture, stack, file structure or server details at the start.

### Exercise style

Course checks should be click-based with ready answers.

Avoid:
- free-form textarea practice;
- asking the user to manually write complete Codex prompts;
- making the user design architecture alone;
- making the user read long text-only blocks without interaction.

### Visual style

Course should be visual and structured:
- cards;
- schemes;
- clear headings;
- short blocks;
- interactive checks;
- no raw English service labels in Russian UI.

Potential visual references:
- DAIR lesson-generator;
- ClassBuild;
- HyperFrames.

## COURSE_METHOD_SPEC_UPDATE_20260603_COURSE_LESSONS_SEMANTIC_BLOCKS

### Current course rule set

The current course section is the draft course “Работа с ИИ” in the app repo branch `design/product-story-03`.

Use this method for the current lessons:

- beginner-facing theory and click-based checks only;
- simple Russian;
- explain meanings and purpose, not deep internal architecture;
- ChatGPT is the leading technical specialist in the method;
- Codex is the technical executor of exact tasks;
- user owns the goal and accepts/rejects by facts;
- lessons 1–9 must be visually split into semantic blocks/cards;
- key terms should be highlighted in the lesson body;
- do not add finance, Telegram, receipt/photo, voice, or multi-agent product cases;
- lesson 4 must preserve the starter prompt controls and the corrected deploy-key logic;
- copied/downloaded markdown prompt files are backup copies for the user, not repo transfer;
- the working repo documents are created by Codex from text embedded in ChatGPT-prepared Codex prompts;
- Git must be taught as history/check/rollback safety at owner level, not as internals-only knowledge.

## COURSE_METHOD_SPEC_UPDATE_20260608_LESSON_7_PREFIX_PROMPTS_VERIFIED

### Current course rule set

- The current course still has 9 numbered lessons plus a visible final section.
- The current lesson order in source is 4: `Codex, AGENTS.md, Skills, токены и роль модели`; 5: `PowerShell, Terminal и подключение к серверу`; 6: `Старт проекта: сначала документация, потом разработка`.
- Lesson 7 is `Процесс работы` and must teach `run`, `design run`, `fix run`, `proof run`, `context`, `context window`, and `prefix`-extension practice.
- The starter prompt panel in lesson 7 is read-only reference content with copy/download actions; it is not free-form student composition practice.
- Lesson 6 and lesson 8 also use starter prompt panels for fixed course tasks, so prompt panels remain part of the course method.
- Continue to keep checks click-based with ready answers.
- Continue to avoid turning the course into free-form textarea practice for student-written prompts.
