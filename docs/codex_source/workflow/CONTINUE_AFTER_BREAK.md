# Continue after break

Purpose:
- resume a docs or app task safely after an interruption.

Rules:
- reread `AGENTS.md`, `docs/codex_source/ENTRYPOINT_FOR_CHATGPT.md`, and the exact task prompt
- confirm the git branch, `HEAD`, and `git status` before editing
- re-read only the exact docs needed for the task
- if proof gates changed while the task was paused, stop and reconcile before editing
- do not resume from stale assumptions or partial memory
- after a break, restate what is proven, what is not, and the next safe step

Notes:
- this is a workflow helper, not a product spec
- docs repair/import runs may create missing docs when required by the task
