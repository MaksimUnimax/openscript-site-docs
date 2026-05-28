# Server Inventory

Initial known facts from previous inventory:

- main app repo: `/opt/ai-starter-community`
- recommended docs repo: `/opt/openscript-site-docs`
- main domain: `https://openscript.ru`
- service: `ai-starter-community-preview.service`
- do not touch Agent Lab or APM for this project
- do not copy runtime/state/logs/tmp/secrets

This file must be updated only from read-only inventory runs.

## Inventory update 2026-05-28 — Relevant repos

Current relevant docs repo:

`/opt/openscript-site-docs`

Current main app repo:

`/opt/ai-starter-community`

Repos explicitly out of scope for current OpenScript site docs work unless a future task says otherwise:

- `/opt/openscript-agent-lab`
- `/opt/autopostmanager`
- `/opt/opendesign-lab/open-design`

Rules:

- Do not copy runtime/state/logs/tmp/secrets into docs.
- Do not read or print `.env` values.
- Do not treat runtime state as source-of-truth.
- Do not change nginx/systemd/env from docs runs.
- For app work, first run read-only proof of `/opt/ai-starter-community`.
