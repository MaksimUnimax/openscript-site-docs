# Frontend Design Skills Evaluation Plan

This plan is for the future comparison of imported UI/design/frontend reference skills.

## Goal

Pick one candidate, apply it to a temporary OpenScript lesson UI skill in the app repo, and evaluate whether it improves lesson presentation without breaking the course contract.

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
2. Create or apply a temporary OpenScript lesson UI skill in the app repo.
3. Apply it to Lesson 1 only.
4. Check the rendered result for:
   - no raw markdown leakage
   - no broken `.md` answer links as the primary path
   - quiz / check blocks working
   - checklist items readable and clickable where appropriate
   - mobile readability
   - clear visual hierarchy
   - accessibility basics
   - tests passing
   - manual browser review
5. If the result is weak, test the next candidate.

## Rules

- Do not install packages without explicit approval.
- Do not call model/provider APIs for this comparison.
- Keep these frontend/design references separate from the course-authoring skill docs.
- Do not import Figma skill artifacts here because no Figma design exists for this project.

## Recommended order

1. manalkaff/opendesign
2. anthropics/frontend-design
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
