# DECISIONS

Confirmed product decisions:
- login remains email OR login
- public registration is temporarily closed
- courses live in "Работа с ИИ" inside the cabinet
- the course shell must not show tariff/payment/ownership noise
- tool and vendor docs must be available locally before tool-based course work
- accepted course content should eventually live in the app repo as git-tracked source, not runtime-only state
- the docs repo is the source-of-truth for future Codex runs
- the first course work is documentation and pipeline design, not app implementation
- app changes only happen in app tasks, not in docs-only runs

Practical scope decisions:
- the current project-memory sync is OpenScript site work, not Agent Lab work
- Agent Lab, APM, Telegram/VK, and OpenDesign Lab are out of scope for this docs snapshot

Future product decisions still open:
- final course structure
- payment/access model
- admin editing workflow
- AI-sales agent behavior

Additional current decisions:
- D007 - Clean exact-copy skills only for active app skills.
  Decision: Active app skills must be clean exact copies from local docs repo sources, unless a future explicit decision creates a project-specific adapter.
  Reason: Custom retellings/adapters caused drift and weak results.
- D008 - Removed custom skill adapters.
  Decision: `openscript-course-authoring` and `openscript-lesson-ui-opendesign` are not active.
  Reason: They were custom retellings/adapters, not clean copied skills.
- D009 - Vercel design guideline skill is docs-reference-only.
  Decision: `vercel-web-design-guidelines` is not active in the app repo.
  Reason: Clean upstream guidance depends on external WebFetch / Fetch latest guidelines, which conflicts with the local-server source rule.
- D010 - Mblode active skill requires companion files.
  Decision: `mblode-agent-skills` may be active only with its companion files copied alongside `SKILL.md`.
  Reason: Its `SKILL.md` references those local companion files.
- D011 - Course work is paused until skill workflow proof.
  Decision: Do not continue lesson generation until one active skill workflow is selected and tested.
  Reason: Earlier lesson/content work was based on weak or custom skill assumptions and must be re-evaluated.
