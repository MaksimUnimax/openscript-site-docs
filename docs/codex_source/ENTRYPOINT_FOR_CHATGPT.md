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
- current project-memory focus is OpenScript site and cabinet course tooling, not Agent Lab, APM, or OpenDesign Lab

Docs repair/import rule:
- normal implementation runs: if required docs are missing, stop and report it
- explicit docs repair/import runs: create or import the missing docs instead of stopping

Canonical doc areas:
- `docs/codex_source/project/**`
- `docs/codex_source/materials/**`
- `docs/codex_source/workflow/**`
- `docs/codex_source/tools/**`
- `docs/codex_source/index.yaml`

## Skills and tool references for Codex prompts

This section is the current source of truth for ChatGPT when preparing Codex prompts that use repo-scoped skills.

### Active app repo skills

Active Codex skills are stored only in the app repo:

    /opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md

Current active clean exact-copy skills:

    $dair-lesson-generator
    $opendesign-manalkaff
    $opendesign-nexu
    $anthropic-frontend-design
    $taste-skill
    $microsoft-frontend-design-review
    $ilm-alan-frontend-design
    $mblode-agent-skills

These are active app skills. They are clean local copies from the local docs repo sources.

### Not active

These must not be used as active skills:

    openscript-course-authoring
    openscript-lesson-ui-opendesign
    vercel-web-design-guidelines

openscript-course-authoring and openscript-lesson-ui-opendesign were removed because they were custom retellings/adapters, not clean copied skills.

vercel-web-design-guidelines is docs-reference-only because the clean upstream skill depends on external WebFetch / Fetch latest guidelines. Do not activate it unless a future task creates a local-safe package.

### How ChatGPT must activate a skill in Codex prompts

Use this generic pattern:

    Use this repo-scoped skill explicitly:
    $<skill-name>

    Read and follow:
    - /opt/ai-starter-community/.agents/skills/<skill-name>/SKILL.md

    STOP_SKILL_NOT_FOUND:
    If the skill file is missing, stop before making changes.

    REPORT:
    Include SKILL_USAGE_PROOF with:
    - skill_name
    - skill_path
    - skill_read
    - rules_applied

Example for DAIR:

    Use this repo-scoped skill explicitly:
    $dair-lesson-generator

    Read and follow:
    - /opt/ai-starter-community/.agents/skills/dair-lesson-generator/SKILL.md

    STOP_SKILL_NOT_FOUND:
    If the skill file is missing, stop before making changes.

### Local docs repo references

The docs repo stores local reference/source copies for skills and tools. These are not automatically active Codex skills.

Main local docs paths:

    /opt/openscript-site-docs/docs/codex_source/tools/dair_lesson_generator/SKILL.md
    /opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/**

Working rule:

    Docs repo files are source/reference copies.
    App repo .agents/skills/** files are active Codex skills.
    Future prompts must use local server paths, not external upstream URLs, when a local copy exists.

### Skill selection rule

Use only one primary skill per controlled Codex run unless the task explicitly requires a second review skill.

For course artifact generation:

    $dair-lesson-generator

For frontend/design experiments, choose one candidate at a time:

    $opendesign-manalkaff
    $opendesign-nexu
    $anthropic-frontend-design
    $taste-skill
    $microsoft-frontend-design-review
    $ilm-alan-frontend-design
    $mblode-agent-skills

Do not mix course generation, app integration, UI implementation, auth, DB, and runtime changes in one uncontrolled run.
