# COURSE METHOD SPEC

This course is for non-programmers who want to learn by following a guided workflow, not by writing free-form Codex prompts from scratch.

Current skill/tooling situation:
- `dair-lesson-generator` is the true active exact-copy skill for standalone multi-lesson browser artifacts
- frontend/design exact-copy skills are available for controlled experiments
- removed custom course-authoring adapters must not be used
- `vercel-web-design-guidelines` is docs-reference-only

Method:
- GPT prepares the prompt
- The user copies and runs it.
- the user brings back the report or output
- the next step is chosen from proof, not guesswork

Learning loop:
- read the docs
- produce a small safe change or proof step
- run the agreed check
- report the result
- move to the next lesson only after the proof is clear

Assignment rules:
- assignments should be tests with ready answers or clear proof criteria
- do not rely on vague "do something useful" tasks
- keep each task small enough to explain and verify

Teaching style:
- visual first
- short blocks of explanation
- concrete examples before abstractions
- use diagrams, cards, steps, callouts, and report examples

Course behavior:
- the user should learn how ChatGPT, Codex, repo docs, and proof runs work together
- the course should prepare the user to run safe documentation/design/fix/report cycles
- the course should not require the user to invent the entire prompt workflow alone
- the next course step must be a controlled experiment, not blind lesson writing
