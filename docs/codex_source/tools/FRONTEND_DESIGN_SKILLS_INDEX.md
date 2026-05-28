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
- `full_local_skill_copy` - complete usable skill text stored locally
- `local_reference_summary` - local docs are summary/reference overviews
- `local_review_reference` - local docs are QA/review references

| Candidate | Local server folder | Local files | full_skill_imported: yes/no | has_local_SKILL_md: yes/no | active_codex_skill: no | docs_reference_only: yes | can_be_used_as_basis_for_app_skill: yes/no/maybe | reason | recommended_next_action |
|---|---|---|---|---|---|---|---|---|---|
| manalkaff/opendesign | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/manalkaff_opendesign/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; good primary candidate for future app-skill conversion | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |
| anthropic/frontend-design | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/anthropic_frontend_design/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; strong aesthetic-direction baseline | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |
| nexu-io/open-design | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/nexu_open_design/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; design-system-backed reference | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |
| vercel web-design-guidelines | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/vercel_web_design_guidelines/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; strong QA/accessibility review reference | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |
| microsoft frontend-design-review | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/microsoft_frontend_design_review/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; review-first accessibility and trust lens | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |
| Ilm-Alan/frontend-design | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/ilm_alan_frontend_design/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; explicit aesthetic-anchor workflow | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |
| mblode/agent-skills | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/mblode_agent_skills/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; broader UI craft and QA family | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |
| Leonxlnx/taste-skill | `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/taste_skill/` | `README.md`, `SKILL.md`, `SUMMARY.md`, `LOCAL_STATUS.md`, `imported_index.md` | yes | yes | no | yes | yes | complete local skill copied from the public project; anti-slop taste and layout discipline | if chosen, adapt into `/opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md` |

This index is a local reference list, not an installation manifest and not a final design decision.
To use a frontend/design candidate in Codex, create or update an app-repo skill using the local docs copy as input.
Do not tell Codex to read external upstream docs when a local copy exists.
