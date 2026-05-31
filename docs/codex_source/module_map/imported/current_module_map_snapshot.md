# Module map snapshot — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
SNAPSHOT_ID: MODULE_MAP_SNAPSHOT_SITE_20260531
SOURCE_KIND: source_derived_app_repo_inventory
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Repo layout

/opt/ai-starter-community/
  source/           — Application source
    app/            — FastAPI application package
      core/           — App factory, config, health
      auth/           — Auth routes, schemas, service, templates
      admin/          — Admin panel routes, CLI, templates
      public_landing/ — Landing page routes, template
      materials/      — Course content, lessons, templates
      user_cabinet/   — User settings, private files, templates
      tariffs/        — Product tariff schemas, service
      paid_options/   — Paid option schemas, service
      payments/       — Payments (structure only)
      notifications/  — Email outbox, SMTP adapter
      shared/         — DB helpers, security, base templates
      ai_sales_agent/ — AI agent (structure only)
      static/         — Static CSS, images
    tests/            — pytest test suite (25+ test files)
  runtime/          — Runtime state (gitignored except .gitkeep)
  state/            — SQLite DB at state/ai_starter_community.sqlite3 (gitignored except .gitkeep)
  logs/             — Log output (gitignored except .gitkeep)
  backups/          — Manual backups (gitignored except .gitkeep)
  tmp/              — Temporary files (gitignored except .gitkeep)
  docs/             — Local docs (gitignored except .gitkeep)
  .agents/          — AI agent skill definitions

## Module dependencies

FastAPI app factory mounts:
- health_router   -> GET /healthz, /readyz
- landing_router  -> GET /
- auth_router     -> GET/POST /register, /login, /logout, /verify-email/{token}, /forgot-password, /reset-password/{token}, /check-email, /resend-verification
- cabinet_router  -> GET /cabinet, /settings
- materials_router-> GET /materials, /materials/lessons/{slug}
- admin_router    -> GET/POST /admin/* (dashboard, tariffs, options, users)

Static files mounted at /static.

## Safe boundaries

- source/app/ is application code
- source/tests/ is test code
- runtime/, state/, logs/, backups/, tmp/ are NOT source of truth
- .env files and secrets are gitignored
- .agents/ contains AI skill defintions (read-only during docs runs)
