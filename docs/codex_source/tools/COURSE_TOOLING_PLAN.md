# COURSE TOOLING PLAN

This plan describes the first path for OpenScript course tooling.

Primary path:
- use a docs-informed workflow first
- shape the first course artifact in the style of DAIR lesson-generator
- produce a structured course plan and lesson content before app integration

Secondary tools:
- ClassBuild: evaluate later for richer full-course generation and teaching packs
- HyperFrames: later visual/video snippets and HTML-to-video experiments
- Skill-Anything: later source-to-study-pack and quiz/flashcard generation
- LiaScript: fallback Markdown-first interactive format
- Codex Skills: future reusable local skills for repeatable course generation

Storage boundary:
- tool docs live in `/opt/openscript-site-docs/docs/codex_source/tools/**`
- accepted course source will later live in `/opt/ai-starter-community` as git-tracked app source
- generated drafts may exist temporarily, but they are not source-of-truth
- there is no course DB schema yet
- course content should not live only in runtime state

Next recommended run:
- `COURSE_CONTENT_PIPELINE_DESIGN_ONLY` for `/materials` and `/cabinet`

Not next:
- app implementation
- payment work
- course rendering work
- DB schema work
- admin editor work
