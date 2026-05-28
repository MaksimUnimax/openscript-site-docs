# DAIR lesson-generator

Source URLs:
- upstream repo: https://github.com/dair-ai/dair-academy-plugins
- raw skill: https://raw.githubusercontent.com/dair-ai/dair-academy-plugins/main/plugins/lesson-generator/skills/lesson-generator/SKILL.md

Date checked:
- 2026-05-28

What it does:
- builds compact standalone multi-lesson course artifacts
- organizes lessons with navigation, objectives, flashcards, quizzes, and source links
- expects a self-contained browser artifact rather than a backend app

Why it matters for OpenScript:
- this is the primary reference for the first course draft inside "Работа с ИИ"
- it matches the kind of compact, guided learning artifact the site needs first

Setup/install notes:
- not performed in this docs run
- the upstream skill writes a browser artifact in `index.html`, `styles.css`, and `script.js`
- no project install was attempted here

Required secret categories:
- none documented in the imported skill

Current status:
- `imported_reference`

Workflow fit:
- first course draft path
- good for lesson plans, quizzes, source links, and compact navigation

What not to do yet:
- do not treat this as final app storage
- do not turn it into a runtime-only workflow
- do not use it to bypass later app integration design
