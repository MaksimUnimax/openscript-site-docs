# AGENTS.md — OpenScript / AI Starter Community: Documentation Repo

This file is the standing repository contract for Codex runs in this repo.

## 1. Repository identity

- Repo: OpenScript / AI Starter Community — public documentation
- Local path: /opt/openscript-site-docs
- Public mirror: MaksimUnimax/openscript-site-docs
- Source of truth: docs/codex_source/**
- App repo (separate): /opt/ai-starter-community
- Production site: https://openscript.ru

## 2. What this repo contains

This repo contains only documentation (docs/codex_source/**) and repo-level config files.
It does NOT contain:
- application source code
- runtime state
- secrets or .env files
- production credentials

## 3. Codex contract

- Codex must not read broad project docs unless the task explicitly specifies exact paths.
- Project docs are interpreted by the human or ChatGPT, not given wholesale to Codex.
- Changes must be minimal, scoped to the task.
- Every change must be committed, pushed, and verified: local HEAD == origin branch HEAD.
- Do not edit application code, runtime, or secrets from this repo.
- Do not touch /opt/openscript-agent-lab or /opt/openscript-agent-lab-docs unless the task explicitly allows.
