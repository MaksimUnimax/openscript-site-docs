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
