# Source vs runtime — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Source of truth

- /opt/ai-starter-community/source/ — application source code (git-tracked)
- /opt/ai-starter-community/staging/start.sh, env.staging.example, README.md — staging support scripts (git-tracked)
- /opt/openscript-site-docs/docs/codex_source/ — documentation (git-tracked)

## Non-source layers

- /opt/ai-starter-community/state/ — production SQLite database (not tracked in git)
- /opt/ai-starter-community/runtime/ — production runtime state (not tracked in git)
- /opt/ai-starter-community/staging/data/ — staging SQLite database (gitignored)
- /opt/ai-starter-community/staging/runtime/ — staging runtime state (gitignored)
- /opt/ai-starter-community/logs/ — application logs (not tracked in git)
- /opt/ai-starter-community/backups/ — manual backups (not tracked in git)
- /opt/ai-starter-community/tmp/ — temporary files (not tracked in git)
- Production service config — nginx, systemd, Docker (NOT_YET_PROVEN)

## Rules

- Runtime data must never be confused with documentation state.
- No production runtime changes without explicit staging proof and manual approval.
- Staging environment (see staging_environment.md) provides the isolated runtime boundary.
- Staging uses separate:
  - data/ directory (staging/data/)
  - runtime/ directory (staging/runtime/)
  - database file (staging/data/ai_starter_community.sqlite3)
  - port (8090, non-default)
  - session cookie name
  - env configuration (staging/env.staging.example)
