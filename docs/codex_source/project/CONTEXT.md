# CONTEXT

Current working context for the OpenScript site docs:

- OpenScript / AI Starter Community is the main site product.
- It is not a course-only repo.
- Courses live inside the "Работа с ИИ" materials area in the personal cabinet.
- The current active block is documentation and project-memory synchronization after skills cleanup.
- `docs/codex_source/**` is the source-of-truth for docs, context, roadmap, decisions, materials specs, workflow rules, and local skill/tool references.
- `/opt/openscript-site-docs` is the docs repo.
- `/opt/ai-starter-community` is the app repo with the active `.agents/skills/**` copies.
- Runtime/server state is not the source of truth.

Current skills state:
- the clean exact-copy active skills are the eight listed in `ENTRYPOINT_FOR_CHATGPT.md`
- `openscript-course-authoring` and `openscript-lesson-ui-opendesign` are not active
- `vercel-web-design-guidelines` is docs-reference-only
- `mblode-agent-skills` is active only with companion files copied alongside `SKILL.md`

Next project direction:
- do not continue generating lessons immediately
- first select one active skill workflow
- run a controlled proof/design experiment
- then adapt the lesson list and first lesson page in the cabinet only after design/proof

Out of scope for this docs update:
- Agent Lab
- APM
- Telegram/VK
- OpenDesign Lab
