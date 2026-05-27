# ChatGPT + Codex Workflow

## Simple model

User -> ChatGPT -> Codex -> Report -> ChatGPT -> User visual check -> Documentation update -> Next step

## User

The user does not need to write code.
The user does not need to understand every technical detail.
The user must understand:
- what is being built;
- what changed;
- what to check;
- whether the result matches the idea.

## ChatGPT

ChatGPT is the guide:
- restores context from docs;
- converts user intent into safe next step;
- prepares Codex prompt;
- reviews Codex report;
- explains result in simple language;
- gives next step.

## Codex

Codex is the executor:
- reads exact docs;
- modifies files when allowed;
- runs checks;
- commits/pushes when requested;
- reports.

