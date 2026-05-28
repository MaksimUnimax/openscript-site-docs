# CONTEXT

Current working context for the OpenScript site docs:

- the site was recovered from a 502 upstream failure in the app repo
- public registration is temporarily closed
- login by email or login is preserved
- the cabinet course shell is prepared
- `/materials` is a safe placeholder
- full app tests passed after the cabinet shell run
- the next step is to prepare course tooling docs before generating course content

Product context:
- OpenScript is one website product, not multiple products
- courses live inside the "Работа с ИИ" materials area in the cabinet
- the cabinet is the place where future course material will be organized

Docs context:
- this repository is the source-of-truth for docs, memory, and tool references
- exact docs must be read before future Codex runs
- docs repair/import runs are allowed to create or import missing docs
- the frontend/design skill reference import exists and is tracked in docs at commit `5be436c03ea1e2da35e5165810d1bbfd63a54018`
- full local frontend/design skill files are now imported and stored under the docs repo local server paths
- the DAIR lesson-generator docs entry is now the full raw local copy, not the earlier summary copy
- the app repo DAIR active skill is being synchronized from that same local raw source
- the app repo active skills are now clean exact copies from local docs repo sources
- the custom `openscript-course-authoring` and `openscript-lesson-ui-opendesign` adapters were removed from the app repo
- the mblode UI-design package now includes companion files locally and the active app copy is complete
- `vercel_web_design_guidelines` is docs-reference-only and not part of the active app skill set

Workflow context:
- do not jump into app implementation yet
- first finish the tooling and method docs
- then do a DESIGN_ONLY course content pipeline run
