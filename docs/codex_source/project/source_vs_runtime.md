# Source vs runtime — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Source of truth

- /opt/ai-starter-community/source/ — application source code (git-tracked)
- /opt/openscript-site-docs/docs/codex_source/ — documentation (git-tracked)

## Non-source layers

- /opt/ai-starter-community/state/ — SQLite database (not tracked in git)
- /opt/ai-starter-community/runtime/ — runtime state (not tracked in git)
- /opt/ai-starter-community/logs/ — application logs (not tracked in git)
- /opt/ai-starter-community/backups/ — manual backups (not tracked in git)
- /opt/ai-starter-community/tmp/ — temporary files (not tracked in git)
- Production service config — nginx, systemd, Docker (NOT_YET_PROVEN)

## Rules

- Runtime data must never be confused with documentation state.
- No production runtime changes without explicit staging proof and manual approval.
- Staging environment must use separate:
  - state/ directory
  - runtime/ directory
  - database file
  - .env configuration
