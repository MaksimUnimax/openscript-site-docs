# Codex Skills

Source URLs:
- official docs: https://developers.openai.com/codex/skills
- reusable skills use case: https://developers.openai.com/codex/use-cases/reusable-codex-skills

Date checked:
- 2026-05-28

What it does:
- lets Codex load reusable skills from repository, user, admin, or system locations
- uses folders that contain `SKILL.md`
- supports enabling/disabling skills and distributing reusable skills via plugins

Why it matters for OpenScript:
- future course-generation workflows can be wrapped into repeatable local skills
- useful once the course pipeline becomes a routine repeatable task

Setup/install notes:
- not performed in this docs run
- the official docs show repo-scoped skills under `.agents/skills`
- user-scoped skills live under `~/.agents/skills`
- admin-scoped skills live under `/etc/codex/skills`

Required secret categories:
- none documented in the imported reference
- do not inspect local Codex auth files from this docs repo

Current status:
- `imported_reference`

Workflow fit:
- future reusable skill layer
- good for packaging a repeatable course workflow after the design is settled

What not to do yet:
- do not inspect personal auth material
- do not treat this as an installed local skill in the absence of a real install step
- do not use it to bypass the docs-first course design stage
