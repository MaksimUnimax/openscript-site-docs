# ClassBuild

Source URLs:
- upstream repo: https://github.com/jtangen/classbuild
- raw README: https://raw.githubusercontent.com/jtangen/classbuild/main/README.md

Date checked:
- 2026-05-28

What it does:
- drafts a complete course from one topic
- can produce reading chapters, slides, quizzes, teaching packs, audio narration, and weekly challenges
- supports a richer course-building pipeline than a lightweight lesson generator

Why it matters for OpenScript:
- useful later when the site needs richer full-course generation and teaching packs
- good reference for batch generation and a more complete learning experience

Setup/install notes:
- not performed in this docs run
- upstream docs show `npm install` and `npm run dev`
- the CLI example expects an API key-based setup

Required secret categories:
- Anthropic Claude API key
- OpenAI API key for image generation, if used
- ElevenLabs API key for audio, if used

Current status:
- `imported_reference`

Workflow fit:
- later evaluation tool
- not the first dependency for the OpenScript course shell

What not to do yet:
- do not install anything here
- do not assume this is the first course authoring path
- do not store course content only in tooling output
