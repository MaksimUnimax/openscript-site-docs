# Current status — OpenScript / AI Starter Community

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community
UPDATED: 2026-06-17
CURRENT_STATUS_ID: CURRENT_STATUS_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED

## Repository separation

- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: fix/carousel-arrow-button-visuals
- Production site: https://openscript.ru

## CURRENT_STATUS_20260616_ISOLATED_COURSE_EDITOR_VERSION_MANAGER_REPAIR

### Current active block

Docs repo memory update for the isolated course editor version manager repair and restore.

### Current live state summary

- Latest saved prior public site state remains the public tariff/access UI iteration accepted and deployed.
- Current explicit user-selected task after that is isolated course editor tooling repair/restoration.
- Isolated editor URL: `http://80.74.29.249:8092/`
- Isolated editor root: `/opt/ai-starter-community/staging/course-editor/current/`
- Editor process reported: `python /opt/ai-starter-community/staging/course-editor/current/server.py`
- Current reported PID after restore: `2793406`
- Editor version registry: `/opt/ai-starter-community/staging/course-editor/current/versions/index.json`
- Editor version storage: `/opt/ai-starter-community/staging/course-editor/current/versions/`
- Editor work copy: `/opt/ai-starter-community/staging/course-editor/current/work/`
- Editor export: `/opt/ai-starter-community/staging/course-editor/current/exports/openscript-universal-method-course-v04-edited.zip`
- Restored version list: `current`, `v01`, `v02`, `v03`, `edited`, `v04`
- The mistaken real-version deletion test reduced the registry to only `v001 / current`.
- Safe source ZIPs remained available and were used for the restore.
- Safe source ZIP recovery locations were `/tmp/course-editor-version-uploads/` and `/tmp/openscript-universal-method-course-*.zip`.
- Editor UI fixes reported as accepted: compact menu, readable dropdown, iframe height/layout, rendered CSS/JS aliases.
- App source and production were not modified.

### Current blocker

Deletion behavior must be proven only with a temporary managed delete-test version. Real versions must not be used for deletion tests.

### Current stop-point

The isolated editor version manager is restored. Next safe step is safe delete proof with a temporary managed version only. Do not resume Kilo/design workflow automatically. Do not run production changes. Do not test delete on real versions. Editor work remains isolated under `/opt/ai-starter-community/staging/course-editor/current/`.

## CURRENT_STATUS_20260615_PUBLIC_TARIFF_ACCESS_UI_ITERATION_ACCEPTED

### Current active block

Docs repo memory update for the accepted live public tariff/access UI iteration.

### Current live state summary

- App branch: fix/carousel-arrow-button-visuals
- Latest accepted/deployed app commit: `eb22b091a2a732966c62e24a93c1799babc3440f` — Keep tariff edit page and scale card typography
- Earlier accepted tariff typography commit: `8a905300739c833ee46ad06383a76d6e65e1c489` — Add tariff typography controls
- Public/authenticated navigation and cabinet/access-gate recovery remain part of the accepted live state.
- Admin tariff CRUD now supports source-backed order, selected-card alignment, and safe integer px typography controls.
- Tariff edit save stays on the same edit page with the notice `Изменения сохранены.`
- New tariff creation redirects to the new tariff edit page with the notice `Тариф создан.`
- Selected tariff cards render via the shared pricing partial and safe CSS custom properties, and large typography no longer overlaps the description.
- The current live tariff/access/UI recovery remains accepted and deployed on the public site.
- Real payment remains NOT_YET_PROVEN.
- Agent Lab remains legacy / no-touch for this docs repo.

### Current stop-point

The live public tariff/access/UI iteration is accepted and deployed. Next safe step is the next explicit user-selected task. Do not start payment, production, Agent Lab, or broad refactor automatically.

## CURRENT_STATUS_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED
UPDATED: 2026-06-14
CURRENT_STATUS_ID: CURRENT_STATUS_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED

## Repository separation

- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: design/product-story-03
- Production site: https://openscript.ru

## CURRENT_STATUS_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED

### Current active block

Docs repo memory update for the accepted course lesson 4/5 polish and accepted admin course ZIP export fixes.

### Current live state summary

- App branch: design/product-story-03
- Latest accepted app commits:
  - `a6c0b277b6e6c35def432cf26b630dd02b161a77` — lesson 4 terminology and lesson 5 cabinet link polished
  - `cf23dda5585e176d9be0075d5e47e557d1ec309d` — all referenced course assets included in export
  - `56d3f0a1a6be067ea1178f3ef3516fe7ff142a0f` — course prompt files exported and manifest sanitized
- Lesson 4 title is now `Codex, AGENTS.md, токены и роль модели`.
- Lesson 4 accepted visible content no longer shows `Skills`, `Skill`, `/skills`, `plugins`, `plugin`, or `/plugins`.
- Lesson 4 uses approved `рабочий шаг (run)` terminology and clarifies `лимиты ресурсов`.
- Lesson 4 slash-command section now teaches only `/status`, `/model`, and `/permissions`, with the `/` menu explanation and arrow-key / Enter guidance.
- Lesson 5 links `личный кабинет курса` and grammatical variants to `https://openscript.ru/cabinet` with `target="_blank"` and `rel="noreferrer"`.
- Admin course export route: `/admin/course-export`.
- Admin course ZIP export facts:
  - 72 total ZIP entries;
  - 51 carousel assets;
  - 2 hero images;
  - 3 prompt markdown files;
  - sanitized `manifest.json` with no absolute server paths.
- Prompt markdown files exported:
  - `prompts/01-start-project-documentation.md` — start-project / documentation prompt;
  - `prompts/02-project-docs-update.md` — project docs update prompt;
  - `prompts/03-new-project-dialogue.md` — new dialogue prompt.
- Current health checks from the acceptance run reported no 500/502 on the relevant live probes.
- The previous `course_practice_carousels_and_vpn_account_block_iteration` block is historical unless the user returns to VPN work.

### Current stop-point

Course lesson 4/5 wording and the admin course ZIP export are accepted. The export now contains course text/source, all referenced carousel assets, hero images, three course prompt markdown files, and a sanitized manifest. Next safe step is the next explicit user-selected task. Do not start payment, production, Agent Lab, or broad app refactor automatically.

## CURRENT_STATUS_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION

### Current active block

Docs repo memory update for the current course carousel and VPN account-block iteration. Manual browser verification is still pending unless the user explicitly confirms acceptance.

### Current live state summary

- App branch: design/product-story-03
- Latest reported app/source facts tied to the current memory update:
  - `2ab492d03a472f26a95d836799c132ca35b5e1c1` — Git carousel screenshots from static assets
  - `91a849344708a3629bfb2be2862e78a9cd02c81c` — Git carousel sizing and labels polished
  - `4755532dcf186d653f132f1e79d43b11f264a4ea` — Git term emphasis and step one label restored
  - `56aac56f3eb30f703b86d82fa40e7e33b27cd7de` — placeholder carousels added to practical lessons
  - `b1e208c4f13f7651772062cb22aaaf6421d4540a` — lesson 6 practice carousel added
  - `3e8e351564b07c154a887e768b1c37711ffb2634` — account grid restored and VPN made a real block type
  - `fbb1477a69ee517ff30736326617e5d4b914b320` — VPN panel polish and account card title fixes; if only in a feature/live-synced branch, treat it as pending branch integration until fast-forwarded
- Active block: `course_practice_carousels_and_vpn_account_block_iteration`
- Course practical carousels are implemented in the course docs memory.
- Lesson 3 Git uses a real screenshot carousel from static assets.
- Lesson 6 project-start carousel was initially missed and then fixed.
- Lesson 7 prefix-extension practice keeps a placeholder carousel pattern.
- Lesson 8 docs update / new-dialog workflow uses the same placeholder carousel pattern when present in source.
- VPN is a real account-block type and does not require login/password.
- The account grid is restored to 4 columns desktop / 2 tablet / 1 mobile.
- VPN video asset is served from `/static/videos/amnezia-vpn-guide.mp4`.
- The polished VPN panel adds Tech Talk attribution and a normal-sized Amnezia button in the reported feature/live-synced state.
- Real payment remains NOT_YET_PROVEN.
- Password-secret encryption policy remains open / not yet proven.
- Agent Lab content is legacy / no-touch and not the current site corpus.

### Current stop-point

Manual browser verification of the latest course carousel and VPN cabinet behavior is still pending unless explicitly confirmed by the user.

### Pending user request

- Move VPN into a separate collapsible block after Accounts.
- Remove the crossed-out instruction line from the VPN block.
- Keep the video inside the collapsible content.
- This request is pending/not proven unless a later report explicitly confirms it.

### Open follow-ups

- Real payment remains NOT_YET_PROVEN.
- Password-secret encryption policy remains open / not yet proven.
- Manual browser verification of the latest course carousel and VPN cabinet behavior remains pending.
- Agent Lab content is legacy / no-touch and not the current site corpus.

### Not next

- Do not treat the separate collapsible VPN block as completed until it is proven.
- Do not move into payment or production work from this docs update.
- Do not use Kilo/design as the current active task unless the user explicitly selects it.

The 2026-06-09 cabinet/account-blocks/paid-options block below is preserved as append-only history.

## Current active block

Docs repo memory update for the verified live cabinet/account-blocks/paid-options iteration. Manual browser verification is still pending unless the user explicitly confirms acceptance.

## Current live state summary

- Latest app commit for the current live cabinet/account-blocks/paid-options iteration: `7c94211819ddb334575d7835152637972930d393`
- Active block: `cabinet_account_blocks_paid_options_live_iteration`
- Paid-options cabinet block is live; real payment processing is still not implemented.
- Server-backed account blocks are live in `/cabinet`.
- Account actions use fetch-based no-jump handling and preserve scroll position.
- Account cards use bounded tracks and do not stretch full width on desktop/tablet when only one card is visible.
- Activation email is wired to the owner user's registered email.
- Real payment remains NOT_YET_PROVEN.
- Password-secret encryption policy remains open / not yet proven.
- Agent Lab content is legacy / no-touch and not the current site corpus.

## Current stop-point

Manual browser verification of the latest cabinet/account-blocks/paid-options behavior is still pending unless explicitly confirmed by the user.

## Accepted live-source commits

- `f10fb8efd2b2d044f66122952675ee66cc0dbd3d` — paid-options hide-base/sort/alignment live deploy
- `3e45d12c1807eae877065459a5c68f762ef02da1` — account_blocks backend/service foundation
- `a16ab80cf354ddfe1a3b48e3d5ee52e716c9b00c` — server-backed cabinet UI and admin/moderator management
- `f67ef013eb831ec76ce3cf69eca40fc8da19d0a8` — moderator assignment for users.role
- `da3ce7f939bffe1cbb802048964c83aae96214a9` — compact card UI and elapsed activation status
- `1a89fd5eea26e955b4f2fe33cfb6e13cf44f3201` — owner selector / action form fixes
- `a3bd97243a267691c6d06403223a470c2fafdefb` — activation email import-cycle/runtime fix
- `7c94211819ddb334575d7835152637972930d393` — no-jump account actions and bounded account card width

## Manual verification status

- Manual browser verification of the latest no-jump/card-width/account-email behavior is still pending unless explicitly confirmed by the user.
- This docs update records the technical deployed state only.
- Real payment processing remains NOT_YET_PROVEN.

## Historical / superseded context

The sections below are preserved append-only history from earlier site and course states.
They are not the current active block and must not be selected as the current stage when the 2026-06-09 cabinet/account-blocks/paid-options status exists above.

## CURRENT_STATUS_20260529_AI_STARTER_COMMUNITY

### Current active block

Repo documentation memory update for the main OpenScript / AI Starter Community site.

### Main project

OpenScript / AI Starter Community is the main product.

Main app repo:
`/opt/ai-starter-community`

Main site:
`https://openscript.ru`

Docs repo:
`/opt/openscript-site-docs`

Public docs repo:
`https://github.com/MaksimUnimax/openscript-site-docs`

### Current source-of-truth correction

Current docs repo may still contain legacy OpenScript Agent Lab framing. This is stale for the current docs task. The canonical active project for this repo must be OpenScript / AI Starter Community.

### App state known from recent reports

Recent successful app commits reported in dialogue include:
- `ae477f553a4292ad9511a48e8c27f2bcfc6bb5c3` — non-course pages aligned with landing theme.
- `604535cb68f4df9fb0bac318f92f939dd6931d18` — landing authenticated state fixed.
- `fe22dca270fcda5d2a4591835f5286f38c6fecba` — authenticated navigation and learning links fixed.
- `f8f14a24052e60e88103344a57b440eda8d2fc40` — course expanded to ten lessons.
- `acbabbe050c2a10b699a32e0f08ad956a1a1a88d` — cabinet settings and auth header identity added.
- `d51ae5f8e7156c4d2a498b463ac0abab38940e75` — learning block layout refined and server-side access tests reported.

These commits are application-repo facts from Codex reports and should not be reproduced as docs repo history.

### Current product rules

- User registers before payment.
- Courses/materials are in the learning/materials section, currently visible as “Обучение”.
- First successful payment in the future must permanently unlock materials.
- Current durable access mechanism is `materials_access_granted_at` / materials access helper.
- Admin access is always open.
- Payment model/success handler is not yet proven/implemented.
- Do not invent payment flow in docs or app tasks.
- Future payment success handler must set the existing durable materials access flag or canonical entitlement derived from it.

### Current cabinet/materials state

`/cabinet` includes:
- account identity in header;
- settings link;
- settings page with password change only;
- learning block above account block;
- two-column learning block:
  - “Обучение” with course entry;
  - “Обучающий проект” with protected file download;
- locked/unlocked state based on server-side access;
- locked state readable but not clickable.

### Current course state

Course has 10 lessons:
1. Как устроена работа с ИИ-разработкой
2. Начало работы с ChatGPT
3. Документация как контроль разработки
4. Обновление документации
5. Новый диалог через документы
6. Git: история, commit, push и откат
7. Как проходит рабочий run Codex
8. PowerShell, Terminal и подключение к серверу
9. Сервер, Codex, AGENTS.md и Skills
10. Ошибки, лайфхаки и правила работы

Course requirements:
- all visible labels in Russian;
- no free-form textarea practice;
- checks should be click-based tests with ready answers;
- ChatGPT prepares Codex prompts;
- user returns Codex report to ChatGPT;
- ChatGPT explains report in simple language;
- course should be visual, not text-only;
- selected lesson is preserved through query parameter, not hash;
- quiz progress counts answered questions, including wrong answers.

### Current stop-point

Docs repo must be refined before broad future app work. The next Codex run should remain docs-only unless the user explicitly switches back to app implementation.

## CURRENT_STATUS_20260604_COURSE_LESSON_SWAP_ACCEPTED

### Current active block

Docs repo memory update for the accepted app course lesson swap and Codex lesson rewrite.

### Accepted app course commit

- `daaa8fcd84d448b94c0f16b5302c90086251b9ac` — Swap course lessons 5 and 6.

### Current course state

Course has 9 lessons:
1. Как устроена работа с ИИ-разработкой
2. Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст
3. Git: история, commit, push и откат
4. Старт проекта: сначала документация, потом разработка
5. Codex, AGENTS.md, Skills, токены и роль модели
6. PowerShell, Terminal и подключение к серверу
7. Старт работы и рабочие run’ы Codex
8. Обновление документации и новый диалог
9. Частые ошибки и правила безопасной работы

### Current accepted scope

- Lesson 5 is now the Codex lesson.
- Lesson 5 scope: Codex as technical executor; ChatGPT manages development; Codex executes instructions; AGENTS.md; Skills; tokens; model choice; mini-model default for ordinary Codex runs; permissions; slash commands; server/workdir context; installation context; good vs bad Codex task; practice; quiz/check; pass criteria; common mistakes.
- Lesson 6 is now the Terminal/server lesson.
- Lesson 6 scope: Terminal; PowerShell; commands; server; SSH; safe commands; dangerous commands; secrets; practice; quiz/check; pass criteria; common mistakes.

### Current stop-point

Course lesson content change is accepted in the app repo.
Docs repo now records that accepted state.
Next safe step is either:
1. user visual review of lessons 5 and 6 on the course page; or
2. if visual review is accepted, choose the next docs/app task from the current product stop-point.

Do not start payment, production, Agent Lab, or broad app work automatically.

## CURRENT_STATUS_20260608_COURSE_ORDER_AND_FINAL_SECTION_REPAIR

### Current active block

Docs repo memory update for the verified current course state and legacy bridge reclassification.

### Verified source inspection

- `source/app/materials/course_content/drafts/dair_smoke_20260529/index.html`
- `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- `source/tests/test_course_rendering.py`

### Accepted app course commit

- `f6f5c2b100296efd69c67fa7387550cf2595340d` — Rewrite lesson 7 process workflow

### Current course state

Course has 9 numbered lessons plus a visible final section:
1. Как устроена работа с ИИ-разработкой
2. Документы проекта: техническое задание (ТЗ), roadmap, правила и контекст
3. Git: история, commit, push и откат
4. Codex, AGENTS.md, Skills, токены и роль модели
5. PowerShell, Terminal и подключение к серверу
6. Старт проекта: сначала документация, потом разработка
7. Процесс работы
8. Обновление документации и новый диалог
9. Частые ошибки, лайфхаки и правила работы
10. Финал курса

### Current lesson 7 scope

- Lesson 7 title: `Процесс работы`.
- Lesson 7 explains `run`, `design run`, `fix run`, and `proof run`.
- Lesson 7 explains one-run/one-task control logic.
- Lesson 7 explains `context` and `context window`.
- Lesson 7 explains `prefix`-extension practice.
- Lesson 7 includes a starter prompt panel for `Prompt для создания расширения`.
- The starter prompt panel has `Смотреть prompt`, `Скопировать prompt`, `Скачать .md`, and a hidden readonly textarea.

### Current prompt panels found in the source

- Lesson 6: starter prompt for project documentation start.
- Lesson 7: starter prompt for prefix-extension practice.
- Lesson 8: starter prompt for docs update.
- Lesson 8: starter prompt for new dialogue.

### Legacy bridge reclassification

- `docs/codex_source/project/module_map.md`, `docs/codex_source/project/project_snapshot.md`, and `docs/codex_source/project/project_overview.md` are legacy/imported history, not current site memory.
- Current site module map: `docs/codex_source/module_map/module_map.md`.
- Current site status: `docs/codex_source/project/current_status.md` and `docs/codex_source/project/CURRENT_STATUS.md`.

### Current stop-point

The current app live state now includes the server-backed cabinet account blocks, moderator assignment, activation email wiring, paid-options cabinet block, no-jump account action handling, and bounded account card width.
Next safe step is manual browser verification of the live cabinet/account-blocks/paid-options behavior, unless the user explicitly confirms acceptance.

## CURRENT_STATUS_20260617_P0_AUTH_HARDENING_SOURCE_FIX_ACCEPTED

### Current active block

Docs repo memory update for the accepted P0 auth hardening source fix on the main app repo.

### Accepted app source fix

- App repo: `/opt/ai-starter-community`
- Branch: `fix/carousel-arrow-button-visuals`
- Commit: `80b8d44d28c21bf5e22cf1674e04c6f5bedcf95b` — `Harden login and session defaults`
- Changed files:
  - `source/app/auth/service.py`
  - `source/app/core/config.py`
  - `source/tests/test_auth_flow.py`

### What changed

- Login brute-force protection is now enforced at the app-service layer.
- Failure policy: 5 failed attempts per 15 minutes.
- The attempt bucket is keyed by normalized email/login and stabilizes to `user:{id}` once the user is known.
- Successful login clears the failure bucket for that identifier.
- Login errors remain non-enumerating at the route layer.
- Session cookies now default to secure in production-like environments.
- `production`, `prod`, and `staging` default to `secure=True`.
- `SESSION_COOKIE_SECURE` still allows an explicit local/dev override.

### Proof

- Targeted auth tests passed: `uv run pytest tests/test_auth_flow.py -q`
- App commit was verified locally and on public GitHub.
- No production deployment or runtime mutation was performed.
- The local rollback backup existed only inside `/opt/ai-starter-community/.codex_backups/pre-p0-auth-security-fix-20260617-055351`.

### Important limitation

- The login rate limiter is process-local in memory.
- This is acceptable as immediate P0 hardening, but it is not final distributed protection for multi-worker or restart-resistant deployments.

### Remaining security priorities

- P1: `password_secret` encryption design/proof with DB/state backup gate.
- P1: CSRF tokens for state-changing forms.
- P1/P2: `change_password()` should revoke active sessions or document the accepted behavior.
- P2: SQLite WAL / busy_timeout hardening.
- P2: admin N+1 owner lookup cleanup.
- P2: duplicated account-block presentation/selection logic.
- P2: admin users pagination.

### Current stop-point

The P0 auth hardening source fix is complete and recorded. The next safe step is `password_secret_encryption_design_proof_with_db_backup_plan`. Do not start production deployment, Agent Lab work, or broader app fixes automatically.

## CURRENT_STATUS_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED

### Current active block

Docs repo memory update for the accepted Phase 1 source-only encryption support for `account_blocks.password_secret` on the main app repo.

### Accepted app source fix

- App repo: `/opt/ai-starter-community`
- Branch: `fix/carousel-arrow-button-visuals`
- Commit: `2b9e13c608c36cf4c44712f59b01dd396dbc17f2` — `Encrypt account block password secrets`
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

### What changed

- Phase 1 source-only encryption support is now implemented for `account_blocks.password_secret`.
- New and updated non-empty `password_secret` values are encrypted before storage.
- Stored envelopes use the versioned format `enc:v1:<nonce_b64>.<ciphertext_b64>`.
- Encryption uses AES-GCM through `cryptography`.
- The nonce is freshly generated and 12 bytes long for each encryption.
- The dedicated runtime key env var is `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY`.
- The expected key format is a base64url-encoded 32-byte key.
- Legacy plaintext rows remain readable for backward compatibility.
- Authorized copy/UI behavior still returns the original secret after decrypt-on-read.
- Empty `password_secret` values remain supported.

### Proof

- Targeted account-block tests passed: `uv run pytest tests/test_account_blocks_service.py tests/test_account_blocks_admin_ui.py tests/test_account_blocks_cabinet_ui.py tests/test_account_blocks_activation.py -q`
- `uv lock --check` passed.
- App commit was verified locally and on public GitHub.
- No production deployment or runtime mutation was performed.
- No live DB migration was performed.
- No real secret rows were read.
- No secrets were read or printed.
- No Agent Lab work was touched.
- The local rollback backup existed only inside `/opt/ai-starter-community/.codex_backups/pre-password-secret-encryption-phase1-20260617-073632`.

### Important limitation

- Existing live plaintext rows are not migrated in this source-only run.
- Runtime key provisioning is not proven by this docs run.
- Production deployment or restart is not proven by this docs run.
- Full at-rest protection for already stored plaintext contents still requires Phase 2 migration.
- Phase 2 migration requires a separate explicit run with a DB/state backup gate and rollback path.

### Remaining security priorities

- P1: Phase 2 migration of existing plaintext `password_secret` rows
- P1: CSRF tokens for state-changing forms
- P1/P2: `change_password()` should revoke active sessions or document the accepted behavior
- P2: SQLite WAL / busy_timeout hardening
- P2: admin N+1 owner lookup cleanup
- P2: duplicated account-block presentation/selection logic
- P2: admin users pagination
- Informational/deployment: SQLite file permissions and server hardening

### Current stop-point

- Phase 1 source-only encryption support is complete and recorded.
- Next safe step: `password_secret_phase2_migration_design_or_preflight_with_db_backup_gate`.
- Do not start production deployment, runtime mutation, Agent Lab work, or broader app fixes automatically.
