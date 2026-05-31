# Current status — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Repository separation

- Docs repo: /opt/openscript-site-docs (this repo)
- App repo: /opt/ai-starter-community
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo remote: github-ai-starter-community:MaksimUnimax/ai-starter-community.git
- Production site: https://openscript.ru

## App repo current state

- Branch: design/product-story-03
- HEAD: f85f5f7ab2ec6ccb4a9834f4797e1db0279c9d66
- Status: 9 untracked files (backups, images, drafts on the feature branch)
- Pre-existing AGENTS.md contract exists.

## Completed docs runs

- site-repo-separation-proof-20260531: repo layout proven, AGENTS.md missing detected
- site-agents-bootstrap-20260531: AGENTS.md created in both repos
- site-docs-currentization-repair-20260531: entrypoint/index.yaml currentized, legacy Agent Lab marked
- site-docs-initial-import-20260531 (this run): source-derived baseline imported

## Source-derived facts

- App is a FastAPI-based web application with Jinja2 HTML templates and SQLite persistence.
- Full user auth flow: registration (currently closed), email verification, login (cookie sessions), password reset.
- Admin panel with tariff/paid-option CRUD, user management, CLI bootstrap.
- Public landing page.
- Educational materials module ( course module "Работа с ИИ" / "Work with AI", currently draft).
- User cabinet with settings and private file storage.
- Email notification via outbox pattern + SMTP adapter.
- Payments module structure exists but implementation state is NOT_YET_PROVEN.
- AI Sales Agent module structure exists but implementation state is NOT_YET_PROVEN.

## Current blocker

No staging/test environment exists. App changes currently go directly to the design/product-story-03 branch without a controlled staging workflow.

## Next safe step

Design and create a test/staging environment proof with separate runtime and test data before any app feature work.

## Staging requirement

Before any Kilo/design-run or app fix-run that touches source, the run must:
1. Prove the staging environment exists.
2. Prove the staging environment is isolated from production.
3. Prove the run will not modify production runtime.
