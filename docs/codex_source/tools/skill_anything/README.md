# Skill-Anything

Source URLs:
- upstream repo: https://github.com/SYuan03/Skill-Anything
- raw README: https://raw.githubusercontent.com/SYuan03/Skill-Anything/main/README.md

Date checked:
- 2026-05-28

What it does:
- converts source material into a structured study pack
- can export a reusable `SKILL.md` package
- supports quiz, flashcards, glossary, learning path, and repo-oriented import/export workflows

Why it matters for OpenScript:
- useful later when the course pipeline needs study-pack generation from docs, repos, PDFs, or other source material
- strong reference for quiz/flashcard-heavy study outputs

Setup/install notes:
- not performed in this docs run
- upstream docs show Python install paths such as `pip install -e ".[all,dev]"` and `pip install skill-anything[all]`
- upstream docs also show optional extras for PDF, video, web, and audio support

Required secret categories:
- OpenAI-compatible API key, if using model-backed generation
- optional compatible API base URL, if the provider is not OpenAI

Current status:
- `imported_reference`

Workflow fit:
- later source-to-study-pack pipeline
- useful when turning source docs into reviewable study materials

What not to do yet:
- do not install packages here
- do not rely on it as the first course shell format
- do not treat exported skills as the only source-of-truth
