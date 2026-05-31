# Safe boundaries — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Source of truth

- docs/codex_source/** in /opt/openscript-site-docs is the docs source of truth
- source/app/** in /opt/ai-starter-community is the application source of truth
- /opt/ai-starter-community/AGENTS.md is the app repo contract

## Not source of truth

- runtime/ (app repo) — runtime state
- state/ (app repo) — SQLite databases
- logs/ (app repo) — application logs
- backups/ (app repo) — manual backups
- tmp/ (app repo) — temporary files
- .env files — environment secrets
- Production service files — nginx, systemd, Docker

## Boundary rules

- Docs-only runs may edit only /opt/openscript-site-docs/docs/codex_source/**
- Before any app source run, the following must be proven:
  1. A staging/test environment exists
  2. The run will not modify production runtime
  3. The app branch and dirty/untracked state are known
- Do not read or print .env, secrets, auth files, tokens, private keys
- Do not delete untracked files in app repo unless explicitly requested
- Do not modify /opt/openscript-agent-lab or /opt/openscript-agent-lab-docs

## Staging requirement

App fix-runs or feature-runs are blocked until a staging environment is proven.
This file must be updated with staging paths once they exist.
