# Materials spec

## MATERIALS_SPEC_UPDATE_20260529_LEARNING_ACCESS_AND_PROJECT_FILE

### Section identity

The materials/learning section is currently visible to users as “Обучение”. It contains the course and the protected student project file.

### Access states

#### Locked user
A locked user is authenticated but not admin and does not have durable materials access.

Locked UI:
- content is readable;
- buttons are disabled;
- no href to course;
- no href to project file;
- message: “Доступ откроется после оплаты.”

Server behavior:
- direct course route blocked;
- direct course content/assets blocked if they expose paid content;
- direct project file route blocked.

#### Unlocked user
An unlocked user is admin or has durable materials access.

Unlocked UI:
- active “Перейти к обучению”;
- active “Скачать файл”.

Server behavior:
- course route allowed;
- protected project file download allowed.

### Access implementation rule

Use existing durable access:
`materials_access_granted_at` / materials access helper.

Do not use:
- email hardcode;
- login hardcode;
- current user id hardcode;
- frontend flag;
- localStorage;
- query parameter;
- CSS-only disabled state.

### Project file rule

The student project file source is public GitHub, but the application must store and serve a protected private copy.

Visible HTML must not contain the GitHub raw URL.

## MATERIALS_SPEC_UPDATE_20260603_COURSE_LESSONS_CURRENT

### Current course/materials state

- Visible area: “Обучение” / “Работа с ИИ”.
- Current draft path: `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- Current state: 9 lessons are implemented as semantic blocks/cards; lesson 4 keeps prompt controls and the corrected deploy-key flow.
- Course checks are theory + tests only for this current draft area.
- Access rules remain unchanged.

## MATERIALS_SPEC_UPDATE_20260608_LESSON_7_AND_PROMPT_PANELS_VERIFIED

### Current course/materials state

- Visible area: “Обучение” / “Работа с ИИ”.
- Current draft path: `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`.
- Current state: 9 numbered lessons plus a visible final section remain implemented as semantic blocks/cards.
- Current lesson order in source is 4: `Codex, AGENTS.md, Skills, токены и роль модели`; 5: `PowerShell, Terminal и подключение к серверу`; 6: `Старт проекта: сначала документация, потом разработка`.
- Lesson 7 is `Процесс работы`.
- Lesson 7 includes `run`, `design run`, `fix run`, `proof run`, `context`, `context window`, and `prefix`-extension practice.
- Lesson 7 includes a starter prompt panel for prefix-extension practice with copy/download actions and a readonly textarea preview.
- Lesson 6 includes the starter prompt panel for project documentation start.
- Lesson 8 includes starter prompt panels for docs update and new dialogue.
- Course checks remain theory + click tests only; the readonly starter prompt textarea is reference content, not student-authored free-form practice.
- Access rules remain unchanged.

## MATERIALS_SPEC_UPDATE_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION

### Current course/materials state

- Visible area remains “Обучение” / “Работа с ИИ”.
- The course now uses visual carousels in practical lessons.
- Real screenshot carousels are used where screenshots already exist.
- Placeholder carousels are used where screenshots are still pending.
- Carousel controls are scoped per carousel instance.
- Lesson 3 Git uses the real screenshot carousel from `/static/course-assets/dair-smoke-20260529/git-carousel/`.
- Lesson 6 project-start uses a placeholder carousel that was added after the first pass missed it.
- Lesson 7 prefix-extension uses the placeholder carousel pattern.
- Lesson 8 docs update / new-dialog uses the same placeholder carousel pattern when present in source.
- Course checks remain theory + click-based only; the README-style prompt textarea is reference content, not free-form student practice.
- Access rules remain unchanged.
