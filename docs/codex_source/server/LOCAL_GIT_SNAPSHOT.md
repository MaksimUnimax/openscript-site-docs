# Local Git Snapshot

STATUS: initial

Known prior inventory:
- `/opt/ai-starter-community`
- branch previously seen: `design/product-story-03`
- repo had untracked backup/image artifacts under `source/app/`

Must be re-verified before implementation tasks.

## Git snapshot update 2026-05-28 — Docs repo

Docs repo:

`/opt/openscript-site-docs`

Public remote:

`https://github.com/MaksimUnimax/openscript-site-docs`

SSH remote used on server:

`git@github.com-openscript-site-docs:MaksimUnimax/openscript-site-docs.git`

Known commits:

- Initial docs bootstrap:
  `8c326befa6cfe59f8fd78f42b0d07f2298692f7c`
- Lesson 7 deploy-key explanation:
  `8d3036e94f5bbd3b2abddbce11642200568eab83`

Deploy key:

- created locally for `openscript-site-docs`;
- public key was added to GitHub Deploy keys;
- write access was enabled;
- private key was not printed.

Main app repo remains separate:

`/opt/ai-starter-community`

Do not infer current app state from this docs repo. Run read-only app proof before app work.
