# Current Status

## Known current live app

Main app repo:

`/opt/ai-starter-community`

Main site:

`https://openscript.ru`

Service:

`ai-starter-community-preview.service`

Known public checks from previous inventory:
- `/` returns 200;
- `/healthz` returns 200;
- `/readyz` returns 200.

## Known app features from prior work

- FastAPI modular app foundation exists.
- Registration exists.
- Email verification exists.
- Login/logout exists.
- Password reset exists.
- Roles exist.
- Admin foundation exists.
- Tariffs exist.
- Paid options exist.
- “Работа с ИИ” materials placeholder exists.
- SMTP via Yandex was enabled in previous work.
- Domain and HTTPS were connected.
- Payment is not implemented yet.
- AI-sales agent is not implemented yet.

## Current documentation problem

The main app repo lacks a complete canonical docs/source-of-truth package.
The new docs repo solves this.

## Not in scope now

- no live site changes;
- no app code changes;
- no payment implementation;
- no Agent Lab work;
- no APM work;
- no nginx/systemd/env changes;
- no course HTML generation yet.

