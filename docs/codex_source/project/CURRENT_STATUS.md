# CURRENT STATUS

Latest known app commit:
- `6547fee3eaa2941626283018d6f3e0e5b83477c6`

Commit meaning:
- `Prepare cabinet course shell`

Known public checks after the cabinet shell run:
- public root response was OK
- `/login` was OK
- `/register` remained closed

Known product state:
- `/cabinet` is now a clean course shell
- `/materials` is a safe placeholder
- registration remains temporarily closed
- login still accepts email or login

Docs work status:
- this repository is being repaired for course tooling documentation
- missing core docs are being created now
- frontend/design skill candidates were imported and pushed at `5be436c03ea1e2da35e5165810d1bbfd63a54018`
- full local frontend/design skill files have now been imported for the current candidates under `docs/codex_source/tools/frontend_design_skills/**`
- the DAIR lesson-generator entry is now the full raw local copy, not the earlier summary copy
- the app repo DAIR active skill is being synchronized to the same raw source
- the custom `openscript-course-authoring` and `openscript-lesson-ui-opendesign` adapters were removed from the app repo during the clean-skill pass
- the app repo now uses clean exact-copy active skills copied from the local docs repo sources
- the mblode UI-design package is now complete locally with companion files
- `vercel_web_design_guidelines` remains docs-reference-only until a local-safe package exists

Next recommended step:
- course content pipeline DESIGN_ONLY for `/materials` and `/cabinet`
- not app implementation yet
