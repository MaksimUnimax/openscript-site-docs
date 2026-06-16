# Safe boundaries — OpenScript / AI Starter Community

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community

## Source of truth

- docs/codex_source/** in /opt/openscript-site-docs is the docs source of truth
- source/app/** in /opt/ai-starter-community is the application source of truth
- /opt/ai-starter-community/AGENTS.md is the app repo contract

## Not source of truth

- runtime/ (app repo) - production runtime state
- state/ (app repo) - production SQLite databases
- staging/data/ (app repo) - staging SQLite database (gitignored)
- staging/runtime/ (app repo) - staging runtime state (gitignored)
- logs/ (app repo) - application logs
- backups/ (app repo) - manual backups
- tmp/ (app repo) - temporary files
- .env files - environment secrets
- Production service files - nginx, systemd, Docker
- Agent Lab repos - separate project, no-touch:
  - /opt/openscript-agent-lab
  - /opt/openscript-agent-lab-docs

## Boundary rules

- Docs-only runs may edit only /opt/openscript-site-docs/docs/codex_source/**
- Isolated editor work may modify only /opt/ai-starter-community/staging/course-editor/current/** when explicitly approved for editor tasks
- Docs-only updates must not touch the isolated editor path
- App source /opt/ai-starter-community/source/app/materials/course_content/** remains forbidden unless explicitly approved
- Production remains forbidden
- Before any app source run, the following must be proven:
  1. A staging/test environment exists and is isolated
  2. The run will not modify production runtime
  3. The app branch and dirty/untracked state are known
- Do not read or print .env, secrets, auth files, tokens, private keys, SMTP credentials, or other production credentials
- Do not bind staging to 0.0.0.0
- Do not delete untracked files in app repo unless explicitly requested
- Do not copy production DB/data into staging
- Do not modify /opt/openscript-agent-lab or /opt/openscript-agent-lab-docs
- Proof-only runs must not silently fix and commit unless the prompt explicitly allows a narrow fix

## Production/live change boundary

- Production/live changes in the app repo happened only because the user explicitly approved them in the corresponding technical prompts.
- That approval does not remove the future requirement for explicit user approval before any later production mutation.
- Production DB changes still require a backup, a narrow scope, and explicit approval in the task prompt.
- Docs-only runs must stay inside `/opt/openscript-site-docs/docs/codex_source/**`.

## Staging environment

- Staging root: /opt/ai-starter-community/staging/
- Bind: 127.0.0.1:8090
- Database: staging/data/ai_starter_community.sqlite3
- Startup: staging/start.sh
- See staging_environment.md and staging_proof.md for details.
- App source runs must use the staging environment, never production.
- No nginx, no systemd, no daemon, no public exposure.
