# Current status — OpenScript / AI Starter Community

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community
UPDATED: 2026-06-09
CURRENT_STATUS_ID: CURRENT_STATUS_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION

## Repository separation

- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: design/product-story-03
- Production site: https://openscript.ru

## Current active block

Docs repo memory update for the verified live cabinet/account-blocks/paid-options iteration. Manual browser verification is still pending unless the user explicitly confirms acceptance.

## Verified source inspection

- `source/app/materials/course_content/drafts/dair_smoke_20260529/index.html`
- `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- `source/tests/test_course_rendering.py`

## Accepted course baseline

- Accepted app course commit: `f6f5c2b100296efd69c67fa7387550cf2595340d`
- Lesson 4 title: `Codex, AGENTS.md, Skills, токены и роль модели`
- Lesson 5 title: `PowerShell, Terminal и подключение к серверу`
- Lesson 6 title: `Старт проекта: сначала документация, потом разработка`
- Lesson 7 title: `Процесс работы`
- Course has 9 numbered lessons plus a visible final section (`lesson-10`).

## Current lesson 7 scope

- `run`, `design run`, `fix run`, `proof run`
- one-run/one-task control logic
- `context` and `context window`
- `prefix`-extension practice
- starter prompt panel with `Смотреть prompt`, `Скопировать prompt`, `Скачать .md`, and a readonly textarea preview

## Legacy bridge reclassification

- `docs/codex_source/project/module_map.md`, `docs/codex_source/project/project_snapshot.md`, and `docs/codex_source/project/project_overview.md` are legacy/imported history, not current site memory.
- Current site module map: `docs/codex_source/module_map/module_map.md`.
- Current site status: `docs/codex_source/project/current_status.md` and `docs/codex_source/project/CURRENT_STATUS.md`.

## Current stop-point

The current app live state now includes the server-backed cabinet account blocks, moderator assignment, activation email wiring, paid-options cabinet block, no-jump account action handling, and bounded account card width.
Next safe step is manual browser verification of the live cabinet/account-blocks/paid-options behavior, unless the user explicitly confirms acceptance.

## CURRENT_STATUS_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION

### Verified current live state

- Paid-options cabinet block is live with active add-ons displayed from the database.
- Base AI / GPT tool option is hidden from the add-on activation block.
- Add-ons are ordered by price descending.
- Buy remains a safe placeholder button; real payment processing is still not implemented.
- Server-backed account blocks are live in `/cabinet`.
- LocalStorage is no longer the source of truth for account blocks.
- Account block types supported in UI: ChatGPT, Сервер, Почта.
- Owner is resolved server-side and hidden from the visible UI.
- Manual title and email fields were removed from the account block UI.
- Admin and moderator can create, edit, delete, and activate account blocks.
- Moderator does not gain full admin dashboard rights.
- Activation email is wired to the owner user's registered email.
- Activation text uses elapsed-day wording, not remaining-days wording.
- Account actions use fetch-based no-jump handling and preserve scroll position.
- Account cards use bounded tracks and do not stretch full width on desktop/tablet when only one card is visible.
- Production test-user cleanup was completed with a backup before deletion.
- Password-secret encryption policy remains open / not yet proven.
- Agent Lab content is legacy / no-touch and not the current site corpus.

### Accepted live-source commits

- `f10fb8efd2b2d044f66122952675ee66cc0dbd3d` — paid-options hide-base/sort/alignment live deploy
- `3e45d12c1807eae877065459a5c68f762ef02da1` — account_blocks backend/service foundation
- `a16ab80cf354ddfe1a3b48e3d5ee52e716c9b00c` — server-backed cabinet UI and admin/moderator management
- `f67ef013eb831ec76ce3cf69eca40fc8da19d0a8` — moderator assignment for users.role
- `da3ce7f939bffe1cbb802048964c83aae96214a9` — compact card UI and elapsed activation status
- `1a89fd5eea26e955b4f2fe33cfb6e13cf44f3201` — owner selector / action form fixes
- `a3bd97243a267691c6d06403223a470c2fafdefb` — activation email import-cycle/runtime fix
- `7c94211819ddb334575d7835152637972930d393` — no-jump account actions and bounded account card width

### Manual verification status

- Manual browser verification of the latest no-jump/card-width/account-email behavior is still pending unless explicitly confirmed by the user.
- This docs update records the technical deployed state only.
- Real payment processing remains NOT_YET_PROVEN.
