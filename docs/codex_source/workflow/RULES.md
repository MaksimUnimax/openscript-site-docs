# RULES

Core rules for this docs repo:
- one run = one task
- proof first
- do not guess when docs or source do not prove behavior
- do not read or print secrets, tokens, passwords, cookies, or private keys
- do not make runtime-only fixes
- the docs repo is the source-of-truth memory layer for the project
- app repo changes only happen in app tasks
- vendor/tool dependent work should have local reference docs before it is used

Docs repair/import rule:
- normal implementation runs stop when required docs are missing
- explicit docs repair/import runs are allowed to create or import the missing docs

Scope rule:
- stay inside the allowed repo and allowed paths for the task
- if the task needs more scope, stop and explain why before expanding

Output rule:
- keep reports concrete
- name files, paths, and proof
- do not turn a run into a brainstorming session when the task is proof or repair
