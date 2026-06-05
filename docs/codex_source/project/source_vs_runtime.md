# Source vs runtime — OpenScript / AI Starter Community

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community

## Source of truth

- App source: /opt/ai-starter-community/source/**
- App staging support: /opt/ai-starter-community/staging/start.sh, /opt/ai-starter-community/staging/env.staging.example, /opt/ai-starter-community/staging/README.md
- Docs source: /opt/openscript-site-docs/docs/codex_source/**

## Runtime / not source of truth

- /opt/ai-starter-community/staging/data/**
- /opt/ai-starter-community/staging/runtime/**
- /opt/ai-starter-community/state/**
- /opt/ai-starter-community/runtime/**
- /opt/ai-starter-community/logs/**
- /opt/ai-starter-community/backups/**
- /opt/ai-starter-community/tmp/**

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
