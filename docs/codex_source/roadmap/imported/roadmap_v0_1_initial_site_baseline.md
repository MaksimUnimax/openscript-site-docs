# Roadmap v0.1 — Initial site baseline

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Phase 1: Documentation and bootstrap (current)

- [x] Repository separation proof (site-repo-separation-proof-20260531)
- [x] Root AGENTS.md contracts created (site-agents-bootstrap-20260531)
- [x] Docs repo currentized, legacy Agent Lab marked (site-docs-currentization-repair-20260531)
- [x] Initial source-derived documentation baseline (site-docs-initial-import-20260531 — this run)

## Phase 2: Staging / test design contour (next)

- [ ] Design test/staging environment
- [ ] Create isolated runtime with test data
- [ ] Prove staging does not touch production
- [ ] Write staging proof docs

## Phase 3: Kilo / design workflow

- [ ] Establish Kilo-safe design workflow using the staging environment
- [ ] First design/implementation run targeting a narrow bounded scope
- [ ] Each run proves staging isolation before source changes

## Phase 4: Production handoff (after manual approval)

- [ ] Production deployment only after explicit manual approval
- [ ] No production changes without a completed docs gate, staging proof, and manual approval

## Known blockers

- No staging/test environment exists
- No staging workflow docs exist
- App currently on design/product-story-03 branch with untracked backup files
- Payments and AI Sales Agent modules have structure but implementation NOT_YET_PROVEN
