# Frontend Design Skills Index

Imported reference docs for future UI and lesson-visual testing in OpenScript / AI Starter Community.

Status key:
- `candidate_primary` - strongest first-pass candidates for future OpenScript UI testing
- `candidate_secondary` - useful follow-up candidates
- `review_only` - more useful as QA / review guidance than as the first generation path
- `imported_reference` - local docs are present and usable as references

Figma is excluded from this import because no Figma design exists for the task.

OpenDesign is included and is not considered worse than other options; it is a primary candidate.

Current first candidates for future testing:
1. `manalkaff/opendesign`
2. `anthropics/frontend-design`
3. `nexu-io/open-design`
4. Vercel web-design-guidelines as QA/review
5. Microsoft frontend-design-review as QA/review

| Candidate | Local path | Upstream URL | Type | Codex compatibility | Strength | Risks | Status |
|---|---|---|---|---|---|---|---|
| manalkaff/opendesign | `docs/codex_source/tools/frontend_design_skills/manalkaff_opendesign/` | <https://github.com/manalkaff/opendesign> | portable markdown skill collection | yes | strong primary design skill front door with local workflow and verifier pattern | design-first, may be broader than lesson UI needs | candidate_primary |
| anthropics/frontend-design | `docs/codex_source/tools/frontend_design_skills/anthropic_frontend_design/` | <https://raw.githubusercontent.com/anthropics/skills/main/skills/frontend-design/SKILL.md> | design skill | yes | strong aesthetic direction guidance and anti-generic UI discipline | can still be high-level if not paired with QA | candidate_primary |
| nexu-io/open-design | `docs/codex_source/tools/frontend_design_skills/nexu_open_design/` | <https://github.com/nexu-io/open-design> | open design engine / multi-agent design system | yes | powerful system-level design engine with many agents and skills | heavier research surface, more moving parts | candidate_primary |
| vercel-labs web-design-guidelines | `docs/codex_source/tools/frontend_design_skills/vercel_web_design_guidelines/` | <https://raw.githubusercontent.com/vercel-labs/agent-skills/main/skills/web-design-guidelines/SKILL.md> and <https://raw.githubusercontent.com/vercel-labs/web-interface-guidelines/main/command.md> | review / QA skill | yes | accessibility and interface review guidance | review-only, not a generation path | review_only |
| microsoft frontend-design-review | `docs/codex_source/tools/frontend_design_skills/microsoft_frontend_design_review/` | <https://raw.githubusercontent.com/microsoft/skills/main/.github/skills/frontend-design-review/SKILL.md> | review / QA skill | yes | strong design-review framework with quality pillars | review-first, not the first creative path | review_only |
| Ilm-Alan/frontend-design | `docs/codex_source/tools/frontend_design_skills/ilm_alan_frontend_design/` | <https://github.com/Ilm-Alan/frontend-design> | skill repo | yes | explicit Codex support and clear aesthetic anchors | anchor system may need adaptation for lesson UI | candidate_secondary |
| mblode/agent-skills | `docs/codex_source/tools/frontend_design_skills/mblode_agent_skills/` | <https://github.com/mblode/agent-skills> | multi-skill repo | yes | UI design, animation, typography, audit skills in one place | broader repo, less specific to lesson surfaces | candidate_secondary |
| Leonxlnx/taste-skill | `docs/codex_source/tools/frontend_design_skills/taste_skill/` | <https://github.com/Leonxlnx/taste-skill> | skill repo | yes | anti-slop frontend taste framework with strong layout and motion instincts | best for landings/portfolios; lesson UI needs careful adaptation | candidate_secondary |

Use this index only as a reference list. It is not an installation manifest and it is not a final design decision.
