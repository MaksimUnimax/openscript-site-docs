# CODEX RUN RULES

Use this file as the run-contract template for OpenScript site-docs tasks.

DOCS_TO_READ:
- always read `docs/codex_source/AGENTS.md`
- always read `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`
- read the exact docs named by the task prompt

Allowed scope:
- only the files and directories named by the task prompt
- docs-only tasks may modify docs paths allowed by the prompt
- app tasks may modify app paths only when explicitly allowed

Forbidden scope:
- no secrets
- no runtime changes
- no service restarts
- no app changes in docs-only runs
- no guessing

Checks:
- preflight git state
- inspect only the exact docs needed
- scan changed docs for secret-looking patterns
- run `git diff --check`
- verify the final staged file list before commit

Acceptance:
- the requested docs exist and are useful, not empty stubs
- the canonical docs point to the correct project
- the report states what was created, updated, or imported
- commit and push are proven when source changes are made

Report markers:
- use the required `CHATGPT_REPORT_BEGIN` / `CHATGPT_REPORT_END` block from the task prompt
- include the exact evidence fields requested by the task

Missing docs behavior:
- normal implementation run: stop with a missing-docs report
- explicit docs repair/import run: create or import the missing docs instead of stopping

Commit/push proof:
- add only the allowed files
- verify staged names before commit
- commit with the task-appropriate message
- push and fetch
- prove `HEAD == origin/main` or the task-specific remote target
