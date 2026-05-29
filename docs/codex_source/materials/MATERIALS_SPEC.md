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
