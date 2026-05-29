# ENTRYPOINT FOR CHATGPT

Status: canonical

Start here for ChatGPT/Codex work in this repository.

What this repo is:
- OpenScript / AI Starter Community site docs
- source-of-truth for the docs layer under `docs/codex_source/**`
- the place to keep project memory, materials specs, workflow rules, and imported tool references

What this repo is not:
- the application repo
- runtime state
- a place to change services, nginx, or systemd
- a place to mix in unrelated projects

Read order:
1. `docs/codex_source/index.yaml`
2. exact docs named by the task prompt
3. only the smallest additional docs needed to prove the current state

Course context:
- the main product is the OpenScript / AI Starter Community website
- courses live inside the "Работа с ИИ" materials area in the main cabinet
- courses are not a separate root product

Docs repair/import rule:
- normal implementation runs: if required docs are missing, stop and report it
- explicit docs repair/import runs: create or import the missing docs instead of stopping

Canonical doc areas:
- `docs/codex_source/project/**`
- `docs/codex_source/materials/**`
- `docs/codex_source/workflow/**`
- `docs/codex_source/tools/**`
- `docs/codex_source/index.yaml`

Skills and tool references for Codex prompts

Clean active app skills
- These are exact local copies of full `SKILL.md` files from the docs repo.
- They live in `/opt/ai-starter-community/.agents/skills/**`.
- No custom retellings or adapters are active now.
- Removed/not active: `openscript-course-authoring`, `openscript-lesson-ui-opendesign`.

Active exact-copy skills:
1. `dair-lesson-generator`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/dair_lesson_generator/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/dair-lesson-generator/SKILL.md`
- Purpose: standalone multi-lesson browser artifacts with navigation, objectives, flashcards, quizzes, and source links.

2. `opendesign-manalkaff`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/manalkaff_opendesign/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/opendesign-manalkaff/SKILL.md`
- Purpose: OpenDesign-style frontend direction for lesson UIs.

3. `opendesign-nexu`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/nexu_open_design/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/opendesign-nexu/SKILL.md`
- Purpose: Open Design engine / Codex-friendly design reference.

4. `anthropic-frontend-design`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/anthropic_frontend_design/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/anthropic-frontend-design/SKILL.md`
- Purpose: strong frontend design baseline for lesson presentation.

5. `taste-skill`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/taste_skill/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/taste-skill/SKILL.md`
- Purpose: anti-slop taste, layout, typography, and motion discipline.

6. `microsoft-frontend-design-review`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/microsoft_frontend_design_review/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/microsoft-frontend-design-review/SKILL.md`
- Purpose: accessibility and design-system review lens.

7. `ilm-alan-frontend-design`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/ilm_alan_frontend_design/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/ilm-alan-frontend-design/SKILL.md`
- Purpose: explicit aesthetic anchor and design direction reference.

8. `mblode-agent-skills`
- Docs source: `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/mblode_agent_skills/SKILL.md`
- App path: `/opt/ai-starter-community/.agents/skills/mblode-agent-skills/SKILL.md`
- Purpose: broader UI craft and quality reference, with companion files copied alongside `SKILL.md`.

How ChatGPT should activate a clean active skill:
```text
Use this repo-scoped skill explicitly:
$<skill-name>

Read and follow:
- /opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md

STOP_SKILL_NOT_FOUND:
If the skill file is missing, stop and report before making changes.

REPORT:
Include SKILL_USAGE_PROOF with:
- skill_name
- skill_path
- skill_read
- rules_applied
```

Vendor/reference frontend design skills
- These remain local docs-repo reference copies under `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/`.
- They are source material for the active exact-copy skills above, not the active skills themselves.
- Do not tell Codex to read external upstream docs when a local copy exists. Use the local server path.
- `vercel-web-design-guidelines` remains docs-reference-only and is not active until a local-safe package exists.

Prompt rule for future skill use
- When a future task needs a skill, ChatGPT should explicitly include:
  - skill name
  - exact path
  - why it is needed
  - `STOP_SKILL_NOT_FOUND` condition
  - `SKILL_USAGE_PROOF` report section
  - tests that prove the skill rules were applied

Prompt snippet example:

```text
Use this repo-scoped skill explicitly:
$<skill-name>

Read and follow:
- /opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md

STOP_SKILL_NOT_FOUND:
If the skill file is missing, stop and report before making changes.

REPORT:
Include SKILL_USAGE_PROOF with:
- skill_name
- skill_path
- skill_read
- rules_applied
```

Example for DAIR:

```text
Use this repo-scoped skill explicitly:
$dair-lesson-generator

Read and follow:
- /opt/ai-starter-community/.agents/skills/dair-lesson-generator/SKILL.md

STOP_SKILL_NOT_FOUND:
If the skill file is missing, stop before making changes.

REPORT:
Include SKILL_USAGE_PROOF with:
- skill_name
- skill_path
- skill_read
- rules_applied
```

For local frontend/design reference copies, use the local server path from the docs repo, not an external URL.

If the task prompt conflicts with this entrypoint, follow the task prompt and report the conflict.
