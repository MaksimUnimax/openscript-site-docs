# Roadmap v0.1 — Initial site baseline

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Stage 0: Repo separation and AGENTS bootstrap (completed)

- [x] Repository separation proof (site-repo-separation-proof-20260531)
- [x] Root AGENTS.md contracts created (site-agents-bootstrap-20260531)
- [x] Docs repo currentized, legacy Agent Lab marked (site-docs-currentization-repair-20260531)

## Stage 1: Site docs currentization and source-derived baseline (completed)

- [x] Initial source-derived documentation baseline (site-docs-initial-import-20260531)
- [x] Staging design proof (site-staging-design-only-20260531)
- [x] Staging implementation (site-staging-implementation-20260531)
- [x] Staging policy correction (site-staging-policy-correction-20260531)

## Stage 2: Isolated staging/test contour (completed and health-proven)

- [x] Design test/staging environment
- [x] Create isolated runtime with test data
- [x] Prove staging does not touch production
- [x] Write staging proof docs
- [x] Staging runtime health proven (site-staging-health-proof-20260531)
- [x] healthz: {"ok":true,"service":"ai-starter-community"}
- [x] readyz: {"ok":true,"ready":true}
- [x] Listener: 127.0.0.1:8090 only
- [x] Process stopped after proof
- [x] Port 8090 free after stop

## Stage 3: Design/Kilo workflow on staging (next)

- [ ] Establish Kilo-safe design workflow using the staging environment
- [ ] First design/implementation run targeting a narrow bounded scope
- [ ] Each run proves staging isolation before source changes

## Stage 4: Manual review and screenshot proof (later)

- [ ] Design review via screenshots or browser proof
- [ ] Manual approval before staging-to-production handoff

## Stage 5: Production handoff (later, separate approval)

- [ ] Production deployment only after explicit manual approval
- [ ] No production changes without a completed docs gate, staging proof, and manual approval

## Known blockers (not yet started)

- Design/Kilo workflow configuration not yet defined
- Screenshot/review method not yet decided
- Payments and AI Sales Agent modules have structure but implementation NOT_YET_PROVEN

## 2026-06-03 — Course lessons 1–9 semantic blocks accepted

### Append id

- RM_SITE_COURSE_LESSONS_20260603

### Current completed stage

- Course “Работа с ИИ” lesson content and UI-structure refinement on branch `design/product-story-03`
- Lessons 1–9 were converted into semantic blocks/cards
- Lesson 4 keeps the starter prompt controls and the corrected deploy-key flow
- The final accepted app commit is `a5a2f6ef40338959a659bc9feecf0a23c46a0c70`
- Public GitHub showed 1 file changed, 916 additions, 10 deletions

### Next

- Docs currentization is being completed now
- Then wait for the user-selected next site/course task

### Not current

- Kilo/design workflow is historical unless the user explicitly selects Kilo
- Production deployment remains a separate later concern
- Payments and AI Sales Agent remain not yet proven

<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY source=codex_sync accepted_by_user=yes -->

## 2026-06-05 — Course lesson 7 rewrite accepted; design preflight is next

### Source

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- App branch: design/product-story-03

### Current accepted app state

- Latest accepted course app commit: f6f5c2b100296efd69c67fa7387550cf2595340d
- Commit title: Rewrite lesson 7 process workflow
- Changed files:
  - source/app/materials/course_content/drafts/dair_smoke_20260529/index.html
  - source/app/materials/course_content/drafts/dair_smoke_20260529/script.js
  - source/tests/test_course_rendering.py

### Accepted course state

- Lesson 7 is now "Процесс работы".
- Lesson 7 covers run definition, one run usually solving one task for control, Design run, Fix run, Proof run, context and context window, prefix-extension / Project Prefixer practice, student-kit link, and an updated quiz.
- Lesson 6 next link now points to Lesson 7 "Процесс работы".

### Current stage summary

- Stage 0 — Repo separation and AGENTS bootstrap: COMPLETED
- Stage 1 — Site docs currentization and source-derived baseline: COMPLETED
- Stage 2 — Isolated staging/test contour: COMPLETED and HEALTH-PROVEN
- Stage 2.5 — Course lesson refinement on design/product-story-03: COMPLETED through f6f5c2b100296efd69c67fa7387550cf2595340d
- Stage 3 — Design/Kilo workflow preflight on staging: NEXT
- Stage 4 — Manual review and screenshot proof: LATER
- Stage 5 — Production handoff: LATER, separate approval required

### Current stop-point

- Course lesson refinement is accepted through app commit f6f5c2b100296efd69c67fa7387550cf2595340d.
- Staging/test contour is already health-proven.
- Next safe technical run is site-design-workflow-preflight-20260605.
- Run mode: design-workflow-proof / no app UI changes yet

### Not next

- production deploy
- payment implementation
- AI Sales Agent implementation
- Agent Lab work
- app refactor
- nginx/systemd
- public staging exposure
- direct UI patch without design workflow preflight

<!-- ROADMAP_APPEND_END id=RM_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION source=codex_sync accepted_by_user=yes -->

## 2026-06-09 — Cabinet account-blocks and paid-options live iteration

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the latest live cabinet iteration.
- App repo branch remains `design/product-story-03`.
- Paid-options cabinet block is live and shows active add-ons from the database.
- Base AI / GPT tool option is hidden from the add-on activation block.
- Add-ons are ordered by price descending.
- Buy remains a safe placeholder; real payment processing is still not implemented.
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

### Current completion state

- Paid-options cabinet block live iteration: completed technically, manual browser verification pending
- Account-block backend/UI live iteration: completed technically, manual browser verification pending
- Moderator assignment live iteration: completed technically
- Activation email live iteration: completed technically
- No-jump and bounded-width cabinet UX: completed technically, manual browser verification pending
- Production test-user cleanup: completed technically

### Open follow-ups

- Manual browser verification of the latest no-jump/card-width/account-email behavior
- Real payment processing / entitlement flow
- Password-secret encryption or other secret-storage policy decision

### Not current

- Kilo/design workflow preflight as the active app task
- Payment provider implementation
- Any app repo or runtime change in this docs run
- Agent Lab work

<!-- ROADMAP_APPEND_END id=RM_SITE_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION -->
