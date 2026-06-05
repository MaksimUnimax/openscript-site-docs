# Current status — OpenScript / AI Starter Community

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community
UPDATED: 2026-06-05
CURRENT_STATUS_ID: CURRENT_STATUS_20260605_COURSE_ACCEPTED_DESIGN_PREFLIGHT_READY

## Repository separation

- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: design/product-story-03
- Production site: https://openscript.ru

## Current active block

Design/Kilo workflow preparation for OpenScript / AI Starter Community using proven localhost-only staging.

This does not mean a UI patch is approved.

The next run must be proof-only preflight:
site-design-workflow-preflight-20260605

## Current proven state

- Staging/test contour exists.
- Staging path: /opt/ai-starter-community/staging/
- Staging listener was proven on 127.0.0.1:8090 only.
- /healthz returned {"ok":true,"service":"ai-starter-community"}.
- /readyz returned {"ok":true,"ready":true}.
- Staging process was stopped after proof.
- Port 8090 was free after proof.
- Production runtime was not touched.
- Agent Lab repos were not touched.
- Secrets were not read.
- app commit 6fae69f was a narrow staging wrapper fix during proof and is classified as minor process deviation.

## Accepted course lesson work after previous docs state

The previous docs state was stale and still pointed to an older course app commit.

The latest accepted course app state includes commit:

f6f5c2b100296efd69c67fa7387550cf2595340d — Rewrite lesson 7 process workflow

This commit changed:

- source/app/materials/course_content/drafts/dair_smoke_20260529/index.html
- source/app/materials/course_content/drafts/dair_smoke_20260529/script.js
- source/tests/test_course_rendering.py

Accepted lesson state:

- Lesson 7 is now "Процесс работы".
- Lesson 7 explains run, Design run, Fix run, Proof run.
- Lesson 7 explains one-run/one-task control logic.
- Lesson 7 explains context, context window and prefix-extension practice.
- Lesson 7 includes student-kit reference.
- Lesson 7 quiz was updated.
- Lesson 6 next link points to Lesson 7 "Процесс работы".

## Current blocker

Need to design and run a controlled Kilo/design workflow preflight against staging.

This preflight must decide the exact design workflow method before any UI patch.

## Next safe technical run

site-design-workflow-preflight-20260605

Run mode:

design-workflow-proof / no app UI changes yet

Goal:

- inspect staging availability;
- inspect current UI/materials state as inventory only;
- inspect Kilo local config state if needed;
- decide exact design workflow method;
- produce design/Kilo implementation plan;
- no UI patch;
- no production changes;
- no Agent Lab changes.

## Not current / not approved

- production deployment
- payment implementation
- AI Sales Agent implementation
- Agent Lab work
- APM/autopostmanager work
- OpenDesign Lab work
- public staging exposure
- nginx/systemd changes
- direct UI patch without design preflight
- app source refactor without separate proof/design
