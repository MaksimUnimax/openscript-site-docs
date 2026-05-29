# MATERIALS SPEC

The "Работа с ИИ" materials area is the course home inside the OpenScript cabinet.

Current state:
- placeholder only
- no fake finished access claims
- no fake payment or ownership claims
- course material is part of the main website product, not a separate root product

Expected future state:
- a visual, practical course area
- lessons, tasks, exercises, and references
- content that starts simple and grows progressively
- assignments with ready answers or proof criteria
- no requirement for the learner to invent free-form Codex prompts

Content rules:
- write for beginners
- keep the material visual and readable
- prefer short lessons and clear steps
- keep course text grounded in the current product flow
- do not pretend subscription or paid access logic is complete before the model is ready
- do not rely on removed custom skills for course generation

Implementation boundary:
- the materials area is part of the main website product
- the course content should eventually be committed as app source, not stored only in runtime state
- skill workflow must be selected and proven before new lesson generation continues
