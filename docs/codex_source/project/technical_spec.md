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
