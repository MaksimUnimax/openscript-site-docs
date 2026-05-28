# ENTRYPOINT FOR CHATGPT

Status: canonical

Start here for ChatGPT/Codex work in this repository.

What this repo is:
- OpenScript / AI Starter Community site docs
- source-of-truth for the docs layer under `docs/codex_source/**`
- the place to keep project memory, materials specs, workflow rules, and imported tool references

What this repo is not:
- the application repo
- runtime state
- a place to change services, nginx, or systemd
- a place to mix in unrelated projects

Read order:
1. `docs/codex_source/index.yaml`
2. exact docs named by the task prompt
3. only the smallest additional docs needed to prove the current state

Course context:
- the main product is the OpenScript / AI Starter Community website
- courses live inside the "Работа с ИИ" materials area in the main cabinet
- courses are not a separate root product

Docs repair/import rule:
- normal implementation runs: if required docs are missing, stop and report it
- explicit docs repair/import runs: create or import the missing docs instead of stopping

Canonical doc areas:
- `docs/codex_source/project/**`
- `docs/codex_source/materials/**`
- `docs/codex_source/workflow/**`
- `docs/codex_source/tools/**`
- `docs/codex_source/index.yaml`

If the task prompt conflicts with this entrypoint, follow the task prompt and report the conflict.
