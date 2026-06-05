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

## Staging environment

- Staging root: /opt/ai-starter-community/staging/
- Bind: 127.0.0.1:8090
- Database: staging/data/ai_starter_community.sqlite3
- Startup: staging/start.sh
- See staging_environment.md and staging_proof.md for details.
- App source runs must use the staging environment, never production.
- No nginx, no systemd, no daemon, no public exposure.
