# Frontend Design Skills Index

All current frontend/design candidates live as local docs repo copies. They are not active Codex skills yet.

Local reference copies live under:
- `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/**`

Active app-repo skills live under:
- `/opt/ai-starter-community/.agents/skills/**`

Figma is excluded from this import because no Figma design exists for the task.
OpenDesign is included and is not considered worse than other options; it is a primary candidate.

Current first candidates for future testing:
1. `manalkaff/opendesign`
2. `anthropic/frontend-design`
3. `nexu-io/open-design`
4. Vercel web-design-guidelines as QA/review
5. Microsoft frontend-design-review as QA/review

Status key:
- `candidate_primary` - strongest first-pass candidates for future OpenScript UI testing
- `candidate_secondary` - useful follow-up candidates
- `review_only` - more useful as QA / review guidance than as the first generation path
- `local_reference_summary` - local docs are summary/reference copies
- `local_review_reference` - local docs are QA/review references

| Candidate | Local server folder | Local files | full_skill_imported | active_codex_skill | docs_reference_only | usable_now_as_reference | usable_now_as_$skill | needs_conversion_to_app_skill | recommendation |
|---|---|---|---|---|---|---|---|---|---|
| manalkaff/opendesign | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/manalkaff_opendesign/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | candidate_primary |
| anthropic/frontend-design | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/anthropic_frontend_design/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | candidate_primary |
| nexu-io/open-design | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/nexu_open_design/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | candidate_primary |
| vercel web-design-guidelines | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/vercel_web_design_guidelines/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | review_only |
| microsoft frontend-design-review | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/microsoft_frontend_design_review/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | review_only |
| Ilm-Alan/frontend-design | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/ilm_alan_frontend_design/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | candidate_secondary |
| mblode/agent-skills | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/mblode_agent_skills/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | candidate_secondary |
| Leonxlnx/taste-skill | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/taste_skill/` | `README.md`, `SUMMARY.md`, `imported_index.md` | no | no | yes | yes | no | yes | candidate_secondary |

This index is a local reference list, not an installation manifest and not a final design decision.
To use a frontend/design candidate in Codex, create or update an app-repo skill using the local docs copy as input.
Do not tell Codex to read external upstream docs when a local copy exists.
