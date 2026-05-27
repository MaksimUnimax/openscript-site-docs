# Rules

## Core rules

- One run = one task.
- No guessing.
- No broad changes.
- No secrets.
- No runtime changes from docs repo tasks.
- No touching unrelated repos.
- Proof before fix if facts are missing.
- Design/spec before implementation if scope is unclear.
- User checks visual/product result.
- ChatGPT explains technical reports.

## Role rules

User:
- owns idea;
- makes product decisions;
- checks result visually;
- brings Codex report back to ChatGPT.

ChatGPT:
- reads docs;
- restores context;
- explains simply;
- prepares one Codex prompt;
- checks Codex report;
- updates next step.

Codex:
- executes scoped technical task;
- reads exact docs;
- changes files only in allowed scope;
- reports what changed and what was not done.

## Forbidden

- Do not ask Codex to read all documents.
- Do not ask Codex to infer project from chat attachments.
- Do not mix this repo with OpenScript Agent Lab or APM.
- Do not put secrets into docs.
- Do not use runtime files as source-of-truth.
- Do not generate app code from docs repo unless explicitly requested for a scoped app task.

