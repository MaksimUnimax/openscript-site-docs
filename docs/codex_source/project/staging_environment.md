# Staging environment — OpenScript / AI Starter Community

STATUS: IMPLEMENTED
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-staging-implementation-20260531
DATE: 2026-05-31

## Location

- App repo: /opt/ai-starter-community
- Staging root: /opt/ai-starter-community/staging/
- Startup script: staging/start.sh
- Env template: staging/env.staging.example

## Parameters

| Parameter | Value |
|---|---|
| Bind address | 127.0.0.1 (localhost only) |
| Port | 8090 |
| App env | staging |
| Database path | staging/data/ai_starter_community.sqlite3 |
| Session cookie | ai_starter_community_staging_session |
| Base URL | http://127.0.0.1:8090 |
| Email mode | outbox (no real SMTP) |
| Session cookie secure | false |

## Isolation proof

- Staging directory is gitignored (staging/data/*, staging/runtime/*).
- Staging uses its own SQLite database — cannot collide with production DB.
- Staging binds to 127.0.0.1 only — no public network exposure.
- Staging port 8090 is non-default — cannot collide with default production bind.
- Staging does not read or reference production .env.
- Staging does not use production SMTP credentials (email_mode=outbox).
- Staging runtime data is ephemeral and can be deleted at any time.

## Startup script safety

- Fails if port 8090 is already in use.
- Sources only env.staging.example (non-secret placeholders).
- Never reads production .env.
- Explicitly sets all env vars so no production defaults leak.
- Runs from source/ context with correct Python path.
- Does not daemonize — runs in foreground for safe manual control.

## Rollback

Delete staging runtime and data:

```bash
rm -rf /opt/ai-starter-community/staging/data/*
rm -rf /opt/ai-starter-community/staging/runtime/*
```

The staging scripts and README remain committed in git.
Any source changes made during design work must be committed separately.

## Files

| File | Purpose |
|---|---|
| staging/start.sh | Staging startup script |
| staging/env.staging.example | Non-secret env var template |
| staging/README.md | Staging usage documentation |
| staging/data/.gitkeep | Placeholder for isolated SQLite database |
| staging/runtime/.gitkeep | Placeholder for isolated runtime files |
