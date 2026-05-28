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

Skills and tool references for Codex prompts:

Active app repo skills
- These are real repo-scoped Codex skills that become available only when Codex works from `/opt/ai-starter-community`.

1. `openscript-course-authoring`
- Path: `/opt/ai-starter-community/.agents/skills/openscript-course-authoring/SKILL.md`
- Purpose: writing course lessons for "Работа с ИИ"; requires ready answers, checkable tasks, and explicit proof; ChatGPT designs, Codex executes, user returns report.
- How ChatGPT should activate it:
  - write: `Use this repo-scoped skill: $openscript-course-authoring`
  - and include: `Read and follow: /opt/ai-starter-community/.agents/skills/openscript-course-authoring/SKILL.md`
- Status: active app repo skill exists.

2. `openscript-lesson-ui`
- Status: not active yet unless created later in the app repo.
- Expected future path: `/opt/ai-starter-community/.agents/skills/openscript-lesson-ui/SKILL.md`
- Purpose: lesson UI / верстка quality, raw markdown cleanup, quiz UI, clickable checklist, answer reveal, and visual/browser proof.
- How to activate after creation:
  - write: `$openscript-lesson-ui`
  - then include the exact skill path and ask Codex to follow it.

Vendor/reference frontend design skills
- These are NOT active Codex skills automatically.
- They live in the docs repo as references under `/opt/openscript-site-docs/docs/codex_source/tools/frontend_design_skills/`.
- Candidates: `manalkaff_opendesign`, `nexu_open_design`, `anthropic_frontend_design`, `vercel_web_design_guidelines`, `microsoft_frontend_design_review`, `ilm_alan_frontend_design`, `mblode_agent_skills`, `taste_skill`
- Purpose: choose/test UI and design approaches later, and inform a future OpenScript-specific lesson UI skill.
- Distinction: docs repo vendor/reference skills are reference documents; app repo `.agents/skills/**` are the active Codex skills.

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
$openscript-course-authoring

Read and follow:
- /opt/ai-starter-community/.agents/skills/openscript-course-authoring/SKILL.md

STOP_SKILL_NOT_FOUND:
If the skill file is missing, stop and report before making changes.

REPORT:
Include SKILL_USAGE_PROOF with:
- skill_name
- skill_path
- skill_read
- rules_applied
```

If the task prompt conflicts with this entrypoint, follow the task prompt and report the conflict.
