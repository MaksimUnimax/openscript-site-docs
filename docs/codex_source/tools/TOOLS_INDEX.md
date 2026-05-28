# TOOLS INDEX

Imported reference docs for future course creation work in OpenScript / AI Starter Community.

Status key:
- `imported_reference` - local docs are present and usable as references
- `needs_refetch` - source was not safely fetched yet
- `draft` - local notes only, not a reference import

| Tool | Local docs | Status | Why it matters |
|---|---|---:|---|
| DAIR lesson-generator | `docs/codex_source/tools/dair_lesson_generator/README.md`, `SKILL.md` | full_local_raw_copy | Primary reference for compact lesson/course artifacts; local raw copy is the working source |
| ClassBuild | `docs/codex_source/tools/classbuild/README.md` | imported_reference | Richer course generation, quizzes, slides, and teaching packs |
| HyperFrames | `docs/codex_source/tools/hyperframes/README.md` | imported_reference | Later visual/video snippets and HTML-to-MP4 rendering ideas |
| Skill-Anything | `docs/codex_source/tools/skill_anything/README.md` | imported_reference | Source-to-study-pack and skill export workflow |
| LiaScript | `docs/codex_source/tools/liascript/README.md` | imported_reference | Markdown-first interactive course fallback/reference |
| Codex Skills | `docs/codex_source/tools/codex_skills/README.md` | imported_reference | Reusable local Codex skills for repeatable course workflows |

Clean active app skills are installed separately as exact local copies:

- `/opt/ai-starter-community/.agents/skills/dair-lesson-generator`
- `/opt/ai-starter-community/.agents/skills/opendesign-manalkaff`
- `/opt/ai-starter-community/.agents/skills/opendesign-nexu`
- `/opt/ai-starter-community/.agents/skills/anthropic-frontend-design`
- `/opt/ai-starter-community/.agents/skills/taste-skill`
- `/opt/ai-starter-community/.agents/skills/microsoft-frontend-design-review`
- `/opt/ai-starter-community/.agents/skills/vercel-web-design-guidelines`
- `/opt/ai-starter-community/.agents/skills/ilm-alan-frontend-design`
- `/opt/ai-starter-community/.agents/skills/mblode-agent-skills`

Refresh rule:
- app active copies must be refreshed only from the matching docs-repo local copy
- do not use external upstream URLs as the working source

Frontend/design skill references remain tracked separately from the clean active app skills:

- `docs/codex_source/tools/FRONTEND_DESIGN_SKILLS_INDEX.md`
- `docs/codex_source/tools/FRONTEND_DESIGN_SKILLS_EVALUATION_PLAN.md`

These are local reference copies only; the clean active app skills are exact copies installed under `/opt/ai-starter-community/.agents/skills/**`.
The local reference copies live under `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/**`.
Full local skill files have been imported for all current frontend/design candidates.
Do not tell Codex to read external upstream docs when a local copy exists.

How to use this index:
- start with the tool that matches the course artifact you need
- treat these docs as references, not installed dependencies
- for DAIR, the local raw copy in `docs/codex_source/tools/dair_lesson_generator/SKILL.md` is the working source
- choose the simplest tool that proves the next step
