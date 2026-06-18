# Current status — OpenScript / AI Starter Community

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community
UPDATED: 2026-06-18
CURRENT_STATUS_ID: CURRENT_STATUS_20260618_SECURITY_PERFORMANCE_BACKLOG_COMPLETED_RUNTIME_APPLIED

## Repository separation

- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: fix/carousel-arrow-button-visuals
- Production site: https://openscript.ru

## CURRENT_STATUS_20260618_SECURITY_PERFORMANCE_BACKLOG_COMPLETED_RUNTIME_APPLIED

### Current active block

Docs repo memory update for the completed remaining security/performance backlog fixes on the main app repo and their preview runtime application.

### Current live state summary

- App branch: fix/carousel-arrow-button-visuals
- Latest accepted app commits:
  - `49c9ef228ee7a5f37ac1dc8da581291856cfa044` — `Avoid admin owner lookup N+1`
  - `44d7893428beb55f50b1cd538e842660d59d194a` — `Cover missing-owner admin account block lookup edge`
  - `7f054551aad5a6b4e7c2c6f58dfd5f9ad48eb17b` — `Consolidate account block presentation logic`
  - `9caf6f08579ccbd01ba1cf730347fe36e552d519` — `Add pagination to admin users`
- Admin account-block owner lookup N+1 cleanup is complete; bulk owner lookup and copy-data helper are active in preview.
- Missing-owner mail-block edge is fixed; admin list no longer falls back to per-row owner lookup when the bulk lookup misses.
- Account-block presentation/selection logic is consolidated in shared helpers used by admin and cabinet routes.
- Admin users pagination is live with bounded `COUNT(*)`/`LIMIT`/`OFFSET` queries and preserved filters.
- Preview runtime restarts were applied after the `7f05455...` and `9caf6f0...` source runs.
- Service `ai-starter-community-preview.service` is active.
- Latest runtime MainPID: `3157141`.
- Runtime smoke after the final restart tested 32 GET URLs and reported `TOTAL_5XX: 0`.
- No new traceback or `database is locked` errors were found after the final restart.

### Current completion state

- Tracked security/performance backlog: completed and accepted.
- Current remaining security/performance backlog: none.
- Production/public handoff remains separate and requires explicit approval.

### Current stop-point

- The remaining tracked security/performance backlog is complete and recorded.
- Next safe step is `final_security_performance_review_or_next_product_step`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.

## 2026-06-18 — Historical uploaded 2026-05-31 staging/design input reconciled

- The user-provided `PROJECT_DOCS_UPDATE_INPUT_FOR_CHATGPT_UPDATED_2026_05_31` was imported as historical staging/design context only.
- Its old branch reference `design/product-story-03` and historical next step `site-design-workflow-preflight-20260531` do not override the current `fix/carousel-arrow-button-visuals` / `SITE_20260618_SECURITY_PERFORMANCE_BACKLOG_COMPLETED_RUNTIME_APPLIED` state.
- The later source-tree hygiene commit `beda5a28c0a57242730217e682122b6c5406f5ba` tracked intended tests/assets and local ignore rules, reduced untracked noise from 673 to 5, and left runtime, docs, and DB untouched.
- The remaining 5 untracked files are raw image-export cleanup candidates and require separate user-approved cleanup.
- Agent Lab remains a separate no-touch boundary.

## CURRENT_STATUS_20260617_SQLITE_WAL_BUSY_TIMEOUT_RUNTIME_APPLIED_ACCEPTED

### Current active block

Docs repo memory update for the accepted SQLite WAL / busy_timeout runtime application on the main app repo.

### Current live state summary

- App branch: fix/carousel-arrow-button-visuals
- Latest accepted app commit: `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — `Configure SQLite WAL and busy timeout`
- Runtime apply run completed with DB/state backup gate passed before restart.
- DB/state backup directory: `/opt/ai-starter-community/state_backups/pre-sqlite-wal-runtime-apply-20260617-140653`
- Backed up live DB file: `ai_starter_community.sqlite3`
- Before restart: `ai_starter_community.sqlite3-wal` absent, `ai_starter_community.sqlite3-shm` absent.
- Service restarted: `ai-starter-community-preview.service`
- Service MainPID before: `3087767`
- Service MainPID after: `3106155`
- Service after restart: active running.
- PRAGMA proof used a new app-style connection via `source/app/shared/db.py:get_connection()` to `/opt/ai-starter-community/state/ai_starter_community.sqlite3`.
- Runtime PRAGMA results: `busy_timeout = 5000`, `journal_mode = wal`, `foreign_keys = 1`.
- After restart, `ai_starter_community.sqlite3-wal` and `ai_starter_community.sqlite3-shm` are present.
- GET-only site smoke after restart tested 30 URLs and reported `TOTAL_5XX: 0`.
- No new traceback or `database is locked` errors were found after restart.
- No source modification, docs modification, config modification, migration, rollback, restore, or Agent Lab work was performed in the runtime apply run.

### Current completion state

- SQLite WAL / busy_timeout runtime application: completed and accepted.
- Source fix remains accepted and now active in preview runtime.
- Production/public handoff remains separate and requires explicit approval.

### Remaining security priorities

- P2: admin N+1 owner lookup cleanup.
- P2: duplicated account-block presentation/selection logic.
- P2: admin users pagination.
- Informational/deployment: SQLite WAL hardening is now live in preview; no additional runtime apply is needed for this item.

### Current stop-point

- SQLite WAL / busy_timeout source fix and runtime apply are complete and recorded.
- Next safe step is `admin_n_plus_one_owner_lookup_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.

## CURRENT_STATUS_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED

### Current active block

Docs repo memory update for the accepted SQLite WAL / busy_timeout source fix on the main app repo; runtime application is still pending.

### Current live state summary

- App branch: fix/carousel-arrow-button-visuals
- Latest accepted app commit: `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — `Configure SQLite WAL and busy timeout`
- Changed files:
  - `source/app/shared/db.py`
  - `source/tests/test_db_connection_pragmas.py`
- `source/app/shared/db.py` now centralizes SQLite connection hardening with `SQLITE_BUSY_TIMEOUT_MS = 5000`.
- App-created file-backed SQLite connections now apply `PRAGMA busy_timeout = 5000`, `PRAGMA foreign_keys = ON`, and `PRAGMA journal_mode = WAL`.
- In-memory databases (`:memory:`, `file::memory:`, and URI memory mode) skip WAL and parent-directory creation but still get busy timeout and foreign-key setup.
- `get_connection()` and `initialize_database()` use the same shared helper.
- New test coverage in `source/tests/test_db_connection_pragmas.py` proved file-backed WAL/busy_timeout behavior and safe in-memory handling.
- Targeted `py_compile` and pytest checks passed in the source run.
- The source fix is accepted and pushed, but it is not yet active in the running preview process because runtime restart/reload has not happened.
- Live DB was not touched; no manual SQLite PRAGMA was run against the live preview database.
- No schema migration, runtime config change, or Agent Lab work was performed.

### Current limitation

- The first future runtime apply/restart of the app must be backup-gated because the first file-backed SQLite connection after restart will execute `PRAGMA journal_mode = WAL`, which can create or change WAL-related files and mutate SQLite state.
- `MANUAL_LIVE_DB_PRAGMA_REQUIRED` is `no`.

### Remaining security priorities

- P2: admin N+1 owner lookup cleanup.
- P2: duplicated account-block presentation/selection logic.
- P2: admin users pagination.
- Informational/deployment: first future runtime apply/restart for SQLite WAL hardening requires a DB/state backup gate.

### Current stop-point

- SQLite WAL / busy_timeout source fix is complete and recorded in source.
- Next safe step is `sqlite_wal_busy_timeout_runtime_apply_with_db_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.

## CURRENT_STATUS_20260617_POST_CSRF_EMERGENCY_FIXES_AND_MATERIALS_PREVIEW_ACCEPTED

### Current active block

Docs repo memory update for the accepted session-revocation source fix, the emergency runtime 500 fixes, the materials CSRF helper fix, and the gated public materials preview state on the main app repo.

### Current live state summary

- App branch: fix/carousel-arrow-button-visuals
- Latest accepted app commits:
  - `e7fc37d272ca136418dd7e3a175cbbfb5bb03f96` — Revoke sessions on password change
  - `55ad86e6e1ff6b8dd7fbf015fd8e46e72390fa10` — Fix public landing template request context
  - `e29d591039c46fc4651f49281937f0dd564b8750` — Register CSRF helper for materials templates
  - `b9e928b77ccc1dedf92ea28e85d3e1f96dedf928` — Add gated public preview for selected materials drafts
- `change_password()` now revokes active sessions via the existing `sessions.revoked_at` mechanism.
- Successful password change forces re-login and redirects to `/login?reset=1`; the current session cookie and CSRF cookie are cleared.
- The emergency `/admin/users` 500 was fixed by restarting only `ai-starter-community-preview.service` so the live process loaded the CSRF helper.
- The emergency `/` 500 was fixed in source by removing the duplicate `request` argument from the public landing template helper.
- Authenticated materials draft pages stopped 500ing after the materials Jinja environment registered the shared CSRF helper.
- Gated public preview for selected materials drafts is disabled by default, keyed by `APP_ENV=staging` plus `STAGING_PUBLIC_COURSE_PREVIEW`, and limited to the explicit allowlist:
  - `/materials/drafts/dair-smoke-20260529/`
  - `/materials/drafts/dair-smoke-20260529/styles.css`
  - `/materials/drafts/dair-smoke-20260529/script.js`
- The public preview bypass applies only to GET/HEAD. Unsafe methods remain protected.
- Current preview smoke proof: 30 GET URLs tested, TOTAL_5XX `0`, `/` `200`, `/admin/users` `303` to `/login`, unauthenticated materials draft `303` to `/login`, health endpoints `200`.
- `ai-starter-community-preview.service` is active.
- No fresh tracebacks were observed after the last restart/smoke.
- Authenticated materials coverage in the proof runs was provided by pytest fixtures; no browser cookies were used.
- The session-revocation source run had an honest process deviation: the strict pre-edit backup gate was violated in the app-source run, but no rollback was performed and the source fix remains accepted because the scope was narrow, the public commit exists, tests passed, and no DB/runtime/docs/secrets/Agent Lab work was touched.

### Current limitation

- Production/public handoff remains separate from preview runtime proof.
- The preview public materials gate is intentionally disabled by default and must not be treated as a production default.

### Remaining security priorities

- P2: SQLite WAL / busy_timeout hardening.
- P2: admin N+1 owner lookup cleanup.
- P2: duplicated account-block presentation/selection logic.
- P2: admin users pagination.
- Informational/deployment: production handoff remains separate and unproven.

### Current stop-point

- The post-CSRF emergency fixes and materials public preview state are recorded.
- Next safe step is `sqlite_wal_busy_timeout_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.

## CURRENT_STATUS_20260617_CSRF_SOURCE_FIX_ACCEPTED

### Current active block

Docs repo memory update for the accepted CSRF source fix for browser forms on the main app repo.

### Current live state summary

- App branch: fix/carousel-arrow-button-visuals
- Latest accepted app commit: `c0b4edf58bab56c2669229b873ab2348cea00c2b` — `Add CSRF protection for browser forms`
- Browser-form CSRF protection is now enforced across auth, admin, user_cabinet, and public_landing surfaces.
- Hidden `_csrf_token` fields are rendered in the affected forms.
- Missing or invalid CSRF tokens return 403.
- 29 browser-form POST handlers are protected.
- The source-only fix is complete and was tested successfully.
- No runtime deployment/restart was performed in this docs sync.
- Password-secret Phase 1 source support and preview Phase 2 migration remain complete as separate prior accepted work.

### Current limitation

- Runtime deployment/restart for the CSRF source fix is not proven by this docs update.
- Production/public handoff remains separate.

### Remaining security priorities

- P1: `change_password()` should revoke active sessions or document the accepted behavior.
- P2: SQLite WAL / busy_timeout hardening.
- P2: admin N+1 owner lookup cleanup.
- P2: duplicated account-block presentation/selection logic.
- P2: admin users pagination.
- Informational/deployment: runtime deployment for the source fix remains separate and unproven in this docs sync.

### Current stop-point

- CSRF source fix is complete and recorded.
- Next safe step is `change_password_session_revocation_source_fix_with_backup`.
- Do not start runtime deployment, Agent Lab work, or broader app fixes automatically.

## CURRENT_STATUS_20260617_PASSWORD_SECRET_PHASE2_DB_MIGRATION_COMPLETED

### Current active block

Docs repo memory update for the completed preview DB migration of `account_blocks.password_secret`.

### Current live state summary

- Preview runtime env file `/etc/ai-starter-community/preview.env` now contains `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY`.
- Preview SQLite DB `/opt/ai-starter-community/state/ai_starter_community.sqlite3` was backed up at `/opt/ai-starter-community/state_backups/pre-password-secret-phase2-migration-20260617-081637/ai_starter_community.sqlite3`.
- Pre-migration counts: total `8`, empty `2`, encrypted `0`, plaintext `6`, suspicious `0`.
- Migration updated `6` legacy plaintext rows to `enc:v1:` envelopes.
- Post-migration counts: total `8`, empty `2`, encrypted `6`, plaintext `0`, suspicious `0`.
- Decrypt verification succeeded for `6` encrypted rows with `0` failures.
- `ai-starter-community-preview.service` restarted and is active.
- The service process has the key loaded from `EnvironmentFile`.
- The preview runtime venv had to be synced with `cryptography==49.0.0` and runtime deps because it initially lacked the dependency needed by the Phase 1 source support.
- The targeted account-block tests passed again after the migration.
- No app source commit was created in the migration run.
- No production deployment or public handoff was performed.

### Current limitation

- Production/public deployment is not proven by this docs update.
- Additional security follow-ups remain open.

### Remaining security priorities

- P1: CSRF tokens for state-changing forms.
- P1/P2: `change_password()` should revoke active sessions or document the accepted behavior.
- P2: SQLite WAL / busy_timeout hardening.
- P2: admin N+1 owner lookup cleanup.
- P2: duplicated account-block presentation/selection logic.
- P2: admin users pagination.
- Informational/deployment: runtime key provisioning is complete for preview, but production deployment still needs a separate approval path.

### Current stop-point

- Phase 2 preview DB migration is complete and recorded.
- Next safe step is `csrf_tokens_design_or_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.

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
- The local rollback backup existed only inside `/opt/ai-starter-community/.codex_backups/pre-password-secret-encryption-phase1-20260617-065237`.

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
