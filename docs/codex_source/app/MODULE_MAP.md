# Module Map

Known main app repo:

`/opt/ai-starter-community`

Known source root:

`/opt/ai-starter-community/source`

Known modules from prior project context:

- `app/core` — settings, app factory, health
- `app/shared` — db/security/utils/shared templates/static
- `app/public_landing` — homepage/landing
- `app/auth` — registration, login, logout, email verification, password reset
- `app/notifications` — email outbox and SMTP adapter
- `app/user_cabinet` — personal cabinet
- `app/materials` — “Работа с ИИ” materials access
- `app/tariffs` — tariffs
- `app/paid_options` — paid options
- `app/admin` — admin
- `app/payments` — placeholder/future payments
- `app/ai_sales_agent` — placeholder/future AI-sales agent
- `tests` — tests

This map must be verified by future read-only app proof before implementation tasks.

## Module map update 2026-05-28 — Verification required before app work

The current module map is based on previous project context and must be treated as a working map until verified by read-only app proof.

Known main app repo:

`/opt/ai-starter-community`

Known main source root:

`/opt/ai-starter-community/source`

Known module areas:

- `app/core` — settings, app factory, health.
- `app/shared` — db/security/utils/shared templates/static.
- `app/public_landing` — public homepage and landing.
- `app/auth` — registration, login, logout, email verification, password reset.
- `app/notifications` — email outbox and SMTP adapter.
- `app/user_cabinet` — user cabinet.
- `app/materials` — “Работа с ИИ” materials access.
- `app/tariffs` — tariffs.
- `app/paid_options` — paid options.
- `app/admin` — admin area.
- `app/payments` — future/placeholder payments.
- `app/ai_sales_agent` — future/placeholder AI-sales agent.
- `tests` — test suite.

Before implementation tasks, Codex must verify:
- current branch;
- current HEAD;
- current git status;
- actual module tree;
- current routes;
- current tests;
- current service/public health.
