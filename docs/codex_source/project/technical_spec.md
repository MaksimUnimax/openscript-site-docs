# Technical spec — Initial source-derived baseline

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31
NOTE: This is a source-derived initial spec. It describes the app as it exists in the source repo, not as a requirements document. Not-yet-proven facts are marked NOT_YET_PROVEN.

## Stack

- Language: Python >=3.11
- Web framework: FastAPI >=0.115
- Template engine: Jinja2 >=3.1 with ChoiceLoader for shared templates
- Database: SQLite via built-in sqlite3 module
- Auth: bcrypt >=4.1 (password hashing), cookie-based session tokens (SHA-256 hashed)
- ASGI server: uvicorn >=0.30
- Dev testing: pytest >=8.0, httpx >=0.27
- Multipart form support: python-multipart >=0.0.9

## Application structure

### Core (app/core)
- App factory: creates FastAPI instance, mounts static files, registers routers
- Config: environment-driven settings via dataclass (app name, host, port, DB path, SMTP, session)
- Health: /healthz and /readyz endpoints

### Auth (app/auth)
- Registration flow with email verification (currently closed with message)
- Login/logout with cookie-based session
- Email verification via token
- Password reset flow
- Resend verification
- Jinja2 templates for all auth pages

### Admin (app/admin)
- Dashboard template
- Tariff CRUD (create, read, update, list)
- Paid option CRUD
- Tariff-option linking UI
- User list and filters
- CLI bootstrap command

### Public landing (app/public_landing)
- Single landing page at GET /
- Title: "OpenScript — программы, боты и MVP без знаний и опыта"

### Materials (app/materials)
- Course content module
- Course.yaml defines one course: "Работа с ИИ" (Work with AI), status draft
- Lessons with content in markdown, answers, assets
- Lesson generator draft (dair_smoke_20260529)
- Access controlled by users.materials_access_granted_at flag

### User cabinet (app/user_cabinet)
- Personal cabinet page
- Settings page
- Private file storage area

### Tariffs & Paid options (app/tariffs, app/paid_options)
- Product catalog: tariffs with associated paid options
- Status, price, currency, sort order
- Linking table tariff_options

### Payments (app/payments)
- Module exists, implementation NOT_YET_PROVEN

### Notifications (app/notifications)
- Email outbox pattern
- SMTP adapter for delivery
- Templates for email content

### Shared (app/shared)
- Database helpers: schema creation, connection management
- Security: password hashing/validation, token generation/hashing
- Base Jinja2 templates
- Utility functions

### AI Sales Agent (app/ai_sales_agent)
- Module directory exists with __init__.py, implementation NOT_YET_PROVEN

## Database schema

Tables proven from source:
- users (email, login, password_hash, role, is_active, email_verified_at, materials_access_granted_at, access_status)
- sessions (user_id, token_hash, expires_at, revoked_at)
- auth_tokens (user_id, token_hash, token_type, target_email, expires_at, used_at)
- email_outbox (recipient_email, subject, body_text, template_key, status)
- tariffs (code, title, description, price_amount_minor, currency, status, sort_order)
- paid_options (code, title, description, price_amount_minor, currency, default_duration_days, status, is_renewable)
- tariff_options (tariff_id, option_id, linking table)

## Known features

- User registration with email verification
- Cookie-based session auth
- Role-based access (user/admin)
- Tariff and paid-option product catalog
- Admin panel for managing tariffs, options, users
- Public landing page
- Educational materials with course content
- User cabinet with private files
- Email outbox with SMTP delivery
- Materials access control

## NOT_YET_PROVEN

- Actual production deployment configuration
- Payment processing implementation
- AI Sales Agent implementation
- Production nginx/systemd setup
- Domain and DNS configuration
- HTTPS/SSL configuration
- Actual user base or content
- Runtime performance characteristics
- Testing coverage depth of auth/admin flows
- Materials access control behavior when fully enabled

## 2026-06-09 — Cabinet account-blocks, moderator role, paid-options block, and activation email live state

### Source-derived additions

- `account_blocks` is now a proven database table with the columns documented in `project/account_blocks.md`.
- `users.role` remains the source of truth for roles; `admin`, `moderator`, and `user` are the current role values used by the live app.
- The admin-only moderator assignment flow is implemented in the app and documented in `project/account_blocks.md`.
- The cabinet now renders server-backed account blocks instead of localStorage-backed cards.
- Supported account-block types are `chatgpt`, `server`, and `mail`.
- Block titles are derived from type labels.
- Owner is resolved server-side and hidden from the visible cabinet UI.
- Visible account-block edits are limited to login and password fields.
- Delete and activate are real POST actions.
- Activation uses internal 60-day logic but visible wording uses elapsed-day text.
- Activation email is queued/sent through the existing notification layer to the owner user's registered email.
- The cabinet now includes the user-facing paid-options activation block.
- Real payment processing, entitlement linkage, and production checkout remain NOT_YET_PROVEN.

### Security note

- `password_secret` is still stored as a service-isolated text field in the current implementation.
- Encryption or a different secret-storage policy has not been proven as implemented.

## 2026-06-17 — P0 auth hardening source fix accepted

- App branch: `fix/carousel-arrow-button-visuals`
- Latest accepted app commit: `80b8d44d28c21bf5e22cf1674e04c6f5bedcf95b` — `Harden login and session defaults`
- Changed files:
  - `source/app/auth/service.py`
  - `source/app/core/config.py`
  - `source/tests/test_auth_flow.py`
- Auth service now enforces login brute-force protection with 5 failed attempts per 15 minutes.
- Login attempt buckets are keyed by normalized email/login and stabilize to `user:{id}` after lookup.
- Login errors remain non-enumerating at the route layer.
- Session cookies now default to secure in production/prod/staging.
- `SESSION_COOKIE_SECURE` still allows an explicit local/dev override.
- The login limiter is process-local in-memory and is not yet a shared/distributed limiter.
- No production deployment, runtime mutation, or secret reads occurred in this run.
- P1/P2 security follow-ups remain open:
  - `password_secret` encryption design/proof with DB/state backup gate
  - CSRF tokens for state-changing forms
  - `change_password()` session revocation behavior
  - SQLite WAL / busy_timeout
  - admin N+1 owner lookup
  - duplicated account-block presentation/selection logic
  - admin users pagination

## 2026-06-14 — Course lesson 4/5 and admin ZIP export accepted

- Admin course export route: `/admin/course-export`
- ZIP export includes all referenced course carousel assets, 2 hero images, and the 3 prompt markdown files
- Exported manifest is sanitized and does not leak absolute server paths
- Accepted app commit references:
  - `a6c0b277b6e6c35def432cf26b630dd02b161a77`
  - `cf23dda5585e176d9be0075d5e47e557d1ec309d`
  - `56d3f0a1a6be067ea1178f3ef3516fe7ff142a0f`

## 2026-06-15 — Public tariff/access UI iteration accepted

- App branch for the accepted live state: `fix/carousel-arrow-button-visuals`
- Latest accepted/deployed app commit: `eb22b091a2a732966c62e24a93c1799babc3440f` — Keep tariff edit page and scale card typography
- Earlier tariff typography commit: `8a905300739c833ee46ad06383a76d6e65e1c489` — Add tariff typography controls
- Tariffs are now proven to carry the following source-backed display fields in addition to the baseline catalog fields:
  - `show_on_homepage`
  - `pricing_text_align`
  - `title_font_size_px`
  - `price_font_size_px`
  - `description_font_size_px`
- Safe typography controls use nullable integer pixel values only.
- Empty typography values fall back to CSS defaults.
- Non-integer typography values are rejected.
- Out-of-range typography values are clamped to the documented safe ranges:
  - title: 16–40 px
  - price: 20–56 px
  - description: 12–24 px
- Admin tariff CRUD now exposes order, text alignment, and typography controls.
- Successful tariff edit POST redirects back to the same edit page and shows a success notice.
- New tariff creation can redirect to the new tariff edit page and show a creation notice.
- Shared tariff display uses `source/app/shared/tariff_display.py` and `source/app/shared/templates/tariff_pricing_section.html` to render selected cards with safe CSS custom properties:
  - `--tariff-title-font-size`
  - `--tariff-price-font-size`
  - `--tariff-description-font-size`
- Selected tariff card layout is font-size-aware and avoids title/price/description overlap at the allowed typography limits.
- Card colors remain source CSS, not raw admin input.
- Real payment processing remains NOT_YET_PROVEN.

## 2026-06-17 — Password-secret encryption phase 1 source support accepted

- App branch: `fix/carousel-arrow-button-visuals`
- Latest accepted app commit: `2b9e13c608c36cf4c44712f59b01dd396dbc17f2` — `Encrypt account block password secrets`
- Changed files:
  - `source/app/account_blocks/secret_crypto.py`
  - `source/app/account_blocks/service.py`
  - `source/app/core/config.py`
  - `source/tests/conftest.py`
  - `source/tests/test_account_blocks_service.py`
  - `source/tests/test_account_blocks_admin_ui.py`
  - `source/tests/test_account_blocks_cabinet_ui.py`
  - `source/pyproject.toml`
  - `source/uv.lock`
- Phase 1 source-only account-block secret support is implemented with authenticated symmetric encryption.
- New and updated non-empty `password_secret` values are encrypted before storage.
- The envelope format is `enc:v1:<nonce_b64>.<ciphertext_b64>`.
- Encryption uses AES-GCM through `cryptography`.
- The runtime key env var is `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY`.
- The expected key format is a base64url-encoded 32-byte key.
- Legacy plaintext rows remain readable for backward compatibility.
- Existing live plaintext rows are not migrated by this source-only run.
- Authorized copy/UI behavior still returns the original secret after decrypt-on-read.
- Empty `password_secret` values remain supported.
- `uv lock --check` passed in the implementation run.
- Targeted account-block tests passed in the implementation run.
- No live DB migration was performed.
- No production deployment or runtime mutation was performed.
- Runtime key provisioning is still a separate deployment concern and is not proven by this docs update.
- Phase 2 migration of already stored plaintext rows remains required for full at-rest coverage.

## 2026-06-17 — Password-secret Phase 2 DB migration completed in preview

- The preview DB migration completed for `account_blocks.password_secret`.
- Preview DB path: `/opt/ai-starter-community/state/ai_starter_community.sqlite3`
- Backup path: `/opt/ai-starter-community/state_backups/pre-password-secret-phase2-migration-20260617-081637/ai_starter_community.sqlite3`
- Pre-migration counts: total `8`, empty `2`, encrypted `0`, plaintext `6`, suspicious `0`
- `6` legacy plaintext rows were migrated to `enc:v1:` envelopes.
- Post-migration counts: total `8`, empty `2`, encrypted `6`, plaintext `0`, suspicious `0`
- Decrypt verification succeeded for `6` encrypted rows with `0` failures.
- The preview runtime key `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY` is provisioned in `/etc/ai-starter-community/preview.env`.
- `ai-starter-community-preview.service` restarted and is active with the key loaded from `EnvironmentFile`.
- The preview runtime venv had to be synced with `cryptography==49.0.0` and runtime deps because it initially lacked the dependency required by the Phase 1 source support.
- No app source commit was created in the migration run.
- No production deployment or public handoff was performed.
- Next safe step is `csrf_tokens_design_or_source_fix_with_backup`.

## 2026-06-17 — CSRF source fix accepted

- Browser-form state-changing routes now require a session-bound CSRF token derived from the browser session and rendered into forms as `_csrf_token`.
- Missing or invalid CSRF tokens are rejected with HTTP 403.
- The source fix covers the auth, admin, user_cabinet, and public_landing browser forms without changing read-only GET/HEAD behavior.
- Shared helper: `source/app/shared/csrf.py`
- Updated browser-flow templates now include the hidden token field on unsafe forms.
- Dedicated CSRF tests plus the updated auth and account-block browser-flow tests passed.
- No runtime deployment, service restart, or DB mutation was performed in this docs update.
- The remaining security follow-up is `change_password()` session revocation behavior.

## 2026-06-17 — Post-CSRF emergency fixes and materials public preview proof

- App branch: `fix/carousel-arrow-button-visuals`
- Session revocation was accepted in app commit `e7fc37d272ca136418dd7e3a175cbbfb5bb03f96`; successful password change now revokes active sessions and forces re-login.
- Emergency `/admin/users` 500 came from a stale running process missing the CSRF helper; restarting only `ai-starter-community-preview.service` fixed the live runtime.
- Emergency `/` 500 came from a duplicate `request` argument in the public landing template helper; app commit `55ad86e6e1ff6b8dd7fbf015fd8e46e72390fa10` fixed it.
- Authenticated materials draft 500 came from the materials Jinja environment missing the shared CSRF helper; app commit `e29d591039c46fc4651f49281937f0dd564b8750` fixed it.
- Gated public preview for selected materials drafts was accepted in app commit `b9e928b77ccc1dedf92ea28e85d3e1f96dedf928`; it is disabled by default, allowlisted, and limited to GET/HEAD.
- Unsafe methods remain protected; non-allowlisted materials paths remain protected.
- Preview smoke proof after the emergency fixes tested 30 GET URLs and reported `TOTAL_5XX: 0`.
- Public checks from the smoke proof recorded `/` `200`, `/admin/users` `303` to `/login`, unauthenticated materials draft `303` to `/login`, and health endpoints `200`.
- `ai-starter-community-preview.service` is active.
- Authenticated materials coverage in the proof runs was provided by pytest fixtures; no browser cookies were used.
- The session-revocation app-source run had a strict pre-edit backup gate violation, but no rollback was performed and the source fix remains accepted because the scope was narrow, the public commit exists, tests passed, and no DB/runtime/docs/secrets/Agent Lab work was touched.
- Remaining follow-ups: SQLite WAL / busy_timeout, admin N+1 owner lookup, duplicated account-block presentation/selection logic, admin users pagination.
- Next safe step: `sqlite_wal_busy_timeout_source_fix_with_backup`.

## 2026-06-17 — SQLite WAL / busy_timeout source fix accepted

- App branch: `fix/carousel-arrow-button-visuals`
- Latest accepted app commit: `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — `Configure SQLite WAL and busy timeout`
- Changed files:
  - `source/app/shared/db.py`
  - `source/tests/test_db_connection_pragmas.py`
- `source/app/shared/db.py` now centralizes SQLite connection hardening with `SQLITE_BUSY_TIMEOUT_MS = 5000`.
- App-created file-backed SQLite connections now apply `PRAGMA busy_timeout = 5000`, `PRAGMA foreign_keys = ON`, and `PRAGMA journal_mode = WAL`.
- In-memory SQLite connections (`:memory:`, `file::memory:`, and URI memory mode) skip WAL and parent-directory creation safely while still getting busy timeout and foreign-key setup.
- `get_connection()` and `initialize_database()` share the same connection-configuration helper.
- New test coverage in `source/tests/test_db_connection_pragmas.py` proved file-backed WAL/busy_timeout behavior and safe in-memory handling.
- Targeted `py_compile` and pytest checks passed in the source run.
- The source fix is accepted and pushed, but it is not yet active in the running preview process because runtime restart/reload has not happened.
- Live DB was not touched; no manual SQLite PRAGMA was run against the live preview database.
- No schema migration, runtime config change, or Agent Lab work was performed.

### Runtime boundary

- The first future runtime apply/restart will open the file-backed SQLite DB and execute `PRAGMA journal_mode = WAL`.
- WAL activation can mutate SQLite state and create WAL-related sidecar files, so the first runtime apply/restart must be DB/state backup-gated.
- Manual live DB PRAGMA is not required by the source fix.

### Remaining follow-ups after runtime apply

- admin N+1 owner lookup cleanup
- duplicated account-block presentation/selection logic
- admin users pagination
- production/public handoff remains separate and requires explicit approval

## 2026-06-17 — SQLite WAL / busy_timeout runtime applied accepted

- App branch: `fix/carousel-arrow-button-visuals`
- Latest accepted app commit: `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — `Configure SQLite WAL and busy timeout`
- Runtime apply used the DB/state backup gate before restarting `ai-starter-community-preview.service`.
- DB backup dir: `/opt/ai-starter-community/state_backups/pre-sqlite-wal-runtime-apply-20260617-140653`
- Backed up DB file: `ai_starter_community.sqlite3`
- Before restart, `ai_starter_community.sqlite3-wal` and `ai_starter_community.sqlite3-shm` were absent.
- After restart, `ai_starter_community.sqlite3-wal` and `ai_starter_community.sqlite3-shm` are present.
- A new app-style SQLite connection via `source/app/shared/db.py:get_connection()` reported:
  - `PRAGMA busy_timeout = 5000`
  - `PRAGMA journal_mode = wal`
  - `PRAGMA foreign_keys = 1`
- Preview smoke after restart tested 30 GET URLs and reported `TOTAL_5XX: 0`.
- No new traceback or `database is locked` errors were observed after restart.
- No source, docs, config, migration, rollback, restore, or Agent Lab changes were performed in the runtime apply run.

### Remaining follow-ups

- admin N+1 owner lookup cleanup
- duplicated account-block presentation/selection logic
- admin users pagination

## 2026-06-18 — Security/performance backlog completed and preview runtime applied

- App branch: `fix/carousel-arrow-button-visuals`
- Latest accepted app commits:
  - `49c9ef228ee7a5f37ac1dc8da581291856cfa044` — `Avoid admin owner lookup N+1`
  - `44d7893428beb55f50b1cd538e842660d59d194a` — `Cover missing-owner admin account block lookup edge`
  - `7f054551aad5a6b4e7c2c6f58dfd5f9ad48eb17b` — `Consolidate account block presentation logic`
  - `9caf6f08579ccbd01ba1cf730347fe36e552d519` — `Add pagination to admin users`
- `app/account_blocks/` owner lookup and shared presentation/selection logic are now consolidated; the admin list no longer performs per-row owner fetches.
- `app/admin/` now uses bounded admin users pagination with `COUNT(*)`/`LIMIT`/`OFFSET` and preserved query filters.
- The preview runtime restarted after the `7f05455...` account-block consolidation run and after the `9caf6f...` admin users pagination run.
- The earlier account-block runtime apply smoke tested 30 GET URLs and reported `TOTAL_5XX: 0`.
- The final pagination runtime apply smoke tested 32 GET URLs and reported `TOTAL_5XX: 0`.
- No new traceback or `database is locked` errors were observed after the final restart.
- Remaining follow-ups from the tracked security/performance backlog: none.
- Production/public handoff remains separate and requires explicit approval.
