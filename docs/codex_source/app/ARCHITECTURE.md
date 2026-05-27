# Architecture

## Current known architecture

FastAPI modular monolith.

Main app repo:

`/opt/ai-starter-community`

Source root:

`/opt/ai-starter-community/source`

The app is split by product areas:
- public landing;
- auth;
- cabinet;
- materials;
- tariffs;
- paid options;
- admin;
- notifications;
- payments placeholder;
- AI-sales agent placeholder.

## Architecture rules

- Do not hardcode current user/admin/email/domain as product logic.
- Keep modules responsible for their own domain.
- Do not put mixed responsibilities into shared files.
- Do not use runtime-only changes as normal implementation.
- Do not expose secrets.
- Do not change nginx/systemd/env from normal app tasks.

