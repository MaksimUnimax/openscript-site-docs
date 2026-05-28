# Frontend Design Skills Evaluation Plan

This plan is for future comparison of the imported local UI/design/frontend reference copies.

## Goal

Pick one candidate from the local docs repo copies, create or update a temporary OpenScript lesson UI skill in the app repo using the local docs copy as input, and evaluate whether it improves lesson presentation without breaking the course contract.

## What to compare

Compare the candidate against:
- readability on mobile
- visual hierarchy
- accessibility
- checklist and quiz affordances
- interactive answer reveal behavior
- cleanliness of the code and templates
- whether the output feels like a real learning surface, not a text wall

## Future evaluation loop

1. Pick one candidate from `FRONTEND_DESIGN_SKILLS_INDEX.md`.
2. Use the local server path from the docs repo copy in the prompt.
3. Create or apply a temporary OpenScript lesson UI skill in the app repo using that local docs copy as input.
4. Apply it to Lesson 1 only.
5. Check the rendered result for:
   - no raw markdown leakage
   - no broken `.md` answer links as the primary path
   - quiz / check blocks working
   - checklist items readable and clickable where appropriate
   - mobile readability
   - clear visual hierarchy
   - accessibility basics
   - tests passing
   - manual browser review
6. If the result is weak, test the next candidate.

## Rules

- Do not install packages without explicit approval.
- Do not call model/provider APIs for this comparison.
- Keep these frontend/design references separate from the course-authoring skill docs.
- Use the local server path, not external source links, when describing the candidate in a future prompt.
- Do not import Figma skill artifacts here because no Figma design exists for this project.
- The app-side skill must be created or updated from the local docs copy; do not depend on external URLs in the implementation prompt.

## Recommended order

1. manalkaff/opendesign
2. anthropic/frontend-design
3. nexu-io/open-design
4. Vercel web-design-guidelines as QA/review
5. Microsoft frontend-design-review as QA/review
6. Ilm-Alan/frontend-design
7. mblode/agent-skills
8. Leonxlnx/taste-skill

## Output expectation

The winning candidate should make lesson UIs feel:
- more readable
- more deliberate
- more interactive
- less like prose walls
- better suited to beginner learning flows

The winner is not final forever. It is the best candidate for the next app-side experiment.
