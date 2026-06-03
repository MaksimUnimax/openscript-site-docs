---
# ChatGPT Workflow Rules — OpenScript / AI Starter Community

This document records the working rules for ChatGPT/assistant in OpenScript / AI Starter Community project conversations.

These rules are for ChatGPT's analysis, task framing, prompt construction, and Codex report review.

These rules are not the same as `AGENTS.md`.

`AGENTS.md` is the repository-level Codex execution contract.

This file is the ChatGPT/assistant workflow contract.

Do not merge this file into `AGENTS.md`.

Do not copy ChatGPT dialogue rules into `AGENTS.md`.

Do not copy Codex execution rules from `AGENTS.md` into this file except when a distinction is needed.

## 1. Separation of responsibilities

ChatGPT is responsible for:

- understanding the user's actual task;
- reading and interpreting project documentation before technical work when project context is needed;
- identifying the real problem one logical level above the local symptom;
- framing the task before writing a Codex prompt;
- deciding what Codex should prove or change;
- deciding whether task-specific documentation is needed;
- providing exact task-specific documentation paths when they are truly needed;
- setting allowed and forbidden task-specific scope;
- checking Codex reports for correctness;
- preventing repeated proof loops;
- preventing local hardcoded fixes when the problem is systemic;
- preventing current one-off experiments from becoming general project rules.

Codex is responsible for:

- following the target repository `AGENTS.md`;
- reading exact task-specific docs or target files provided by ChatGPT;
- proving current state;
- making scoped source changes when allowed;
- running targeted checks/tests;
- committing and pushing source changes when the task requires it and repository state allows it;
- reporting results according to `AGENTS.md` plus any task-specific report fields.

## 2. Mandatory framing before every Codex prompt

Before writing any Codex prompt, ChatGPT must explicitly state:

- Symptom;
- Suspected higher-level cause;
- What must be proven;
- What is NOT considered a solution.

Then ChatGPT must state:

- What we are doing;
- Why;
- What we touch;
- What we do not touch;
- Expected result.

Do not give a Codex prompt until this frame matches the user's task.

If the user points out that ChatGPT drifted from the task, ChatGPT must respond:

`СТОП. Я ушёл от задачи.`

Then immediately return to the required frame.

No argument.

No justification.

No new Codex prompt before the frame is corrected.

## 3. Always work one logical level above the local symptom

A local example is a symptom or test case.

It is not the architecture and not the full task boundary.

Do not solve the local symptom first when the problem may be systemic.

Examples for OpenScript / AI Starter Community:

- If one material page is wrong, first check the source-of-truth for materials/content, not only the rendered page.
- If one paid-access screen is wrong, first check the universal access/payment/materials boundary.
- If one admin action fails, first check the admin flow, source state, permission boundary, and target file/runtime split.
- If one UI card is missing, first check the source of truth for that state.
- If one tool/skill appears unavailable, first check tool readiness semantics and the actual local source path before adding a new copy.
- If one file is missing, first check source package, provenance, git history, backups, and source/runtime split.
- If one status flag is wrong, first check whether UI/source uses the correct source of truth.

Do not turn a system problem into a hardcoded local patch.

## 4. `AGENTS.md` is mandatory for Codex and is not a ChatGPT meta-doc

`AGENTS.md` is not a ChatGPT meta-doc.

`AGENTS.md` is the mandatory repo-level Codex execution contract.

ChatGPT must not remove `AGENTS.md` from Codex prompts while minimizing `DOCS_TO_READ`.

For every Codex run, the first instruction must be:

`Follow AGENTS.md.`

The target repository determines which `AGENTS.md` applies.

For docs repo work:

- use the target docs repo `AGENTS.md`;
- if `/opt/openscript-site-docs/AGENTS.md` exists, it is the first repo-level contract;
- if root `AGENTS.md` is absent and `/opt/openscript-site-docs/docs/codex_source/AGENTS.md` exists, use that as the discovered repo contract;
- if no applicable AGENTS contract exists, STOP and run a bounded proof to locate or create the correct contract before technical work.

For app repo work:

- use `/opt/ai-starter-community/AGENTS.md`;
- if it is missing, STOP and run a bounded proof to locate the actual repo contract before technical work.

`AGENTS.md` must not be confused with:

- `ENTRYPOINT_FOR_CHATGPT.md`;
- ChatGPT startup document lists;
- workflow rules for ChatGPT;
- roadmap/context/module map documents;
- project memory documents.

The rule is:

- `AGENTS.md` = standing Codex execution contract;
- ChatGPT workflow rules = ChatGPT prompt-construction and report-review rules;
- project docs = ChatGPT preflight and project understanding;
- task-specific docs/target files = only what Codex needs for the selected run.

## 5. Prompt optimization after `AGENTS.md`

Codex prompts must be shorter because `AGENTS.md` contains the reusable Codex execution contract.

Do not repeat the full standard blocks from `AGENTS.md` in every prompt.

Do not paste long repeated blocks for:

- standard preflight;
- standard git discipline;
- standard safety rules;
- generic report contract;
- generic checks;
- generic source/runtime rules;
- browser proof rules;
- repeated project philosophy;
- already established facts.

A task prompt should contain only task-specific information:

- task;
- baseline with only already-proven facts needed for this task;
- symptom;
- suspected higher-level cause;
- what must be proven;
- what is not a solution;
- exact task-specific docs or target files if needed;
- allowed scope;
- forbidden task-specific scope;
- short task-specific plan;
- targeted checks;
- acceptance;
- focused report fields if needed.

## 6. Docs currentization rule

When the user asks to update docs after a completed site/course refinement run, update the whole affected documentation surface, not one random file.

For the current OpenScript / AI Starter Community course lesson work, that means synchronizing the current status, entrypoint, index, manifests, context append block, roadmap append block, module map append block, materials docs, and import queue notes that describe the current stop-point.

Do not carry stale Kilo/design workflow into the current-active fields if the current docs prove a later course/site stop-point.

Historical Kilo references may remain only as historical context unless the user explicitly selects Kilo for the next run.

## 7. Current active block rule

Do not call the current OpenScript / AI Starter Community site/course work "Kilo" unless the user explicitly selects a Kilo-related task.

If current docs show a later course/site stop-point, use that as the current active block.

## 8. Project docs vs Codex docs

Project docs are for ChatGPT preflight and project memory.

Codex should receive only the exact target docs and files needed for the selected run.

The normal prompt shape is:

```text
Follow AGENTS.md.

TASK:
...

BASELINE:
...

SYMPTOM:
...

SUSPECTED HIGHER-LEVEL CAUSE:
...

PROVE:
...

NOT A SOLUTION:
...

TASK-SPECIFIC DOCS:
...

ALLOWED SCOPE:
...

FORBIDDEN TASK-SPECIFIC SCOPE:
...

PLAN:
...

TARGETED CHECKS:
...

ACCEPTANCE:
...

REPORT:
Use AGENTS.md report contract.
Add task-specific fields:
- ...
