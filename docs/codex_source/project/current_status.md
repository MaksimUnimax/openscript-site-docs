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

## Completed runs

- site-repo-separation-proof-20260531: repo layout proven, AGENTS.md missing detected
- site-agents-bootstrap-20260531: AGENTS.md created in both repos
- site-docs-currentization-repair-20260531: entrypoint/index.yaml currentized, legacy Agent Lab marked
- site-docs-initial-import-20260531: source-derived baseline imported
- site-staging-design-only-20260531: staging design proven (zero source code changes needed)
- site-staging-implementation-20260531: staging support files created, docs updated

## Source-derived facts

- App is a FastAPI-based web application with Jinja2 HTML templates and SQLite persistence.
- Full user auth flow: registration (currently closed), email verification, login (cookie sessions), password reset.
- Admin panel with tariff/paid-option CRUD, user management, CLI bootstrap.
- Public landing page.
- Educational materials module (course module "Работа с ИИ" / "Work with AI", currently draft).
- User cabinet with settings and private file storage.
- Email notification via outbox pattern + SMTP adapter.
- Payments module structure exists but implementation state is NOT_YET_PROVEN.
- AI Sales Agent module structure exists but implementation state is NOT_YET_PROVEN.

## Staging environment

- Staging root: /opt/ai-starter-community/staging/
- Bind: 127.0.0.1:8090
- Database: staging/data/ai_starter_community.sqlite3
- Startup: staging/start.sh
- See staging_environment.md for details.

## Current status

Staging support files are created and committed. Staging has NOT been started yet.
Next step is to start staging locally and verify /healthz.

## Staging requirement

Before any Kilo/design-run or app fix-run that touches source, the run must:
1. Prove the staging environment exists.
2. Prove the staging environment is isolated from production.
3. Prove the run will not modify production runtime.
