# Module map

## MODULE_MAP_UPDATE_20260529_AI_STARTER_COMMUNITY

### Main app repo

Path:
`/opt/ai-starter-community`

### Relevant modules from recent work

#### public_landing
Purpose:
Main public landing page and authenticated landing state.

Recent decisions:
- anonymous users may see “Войти” and “Начать первый проект”;
- authenticated users must not see “Войти” or “Начать первый проект”;
- authenticated users see “Обучение” and “Личный кабинет”;
- authenticated primary learning CTA should lead directly to the course/materials route when access permits.

#### shared templates / static styles
Purpose:
Common non-course layout, header, navigation, buttons, cards, mobile layout.

Recent decisions:
- header must show current account identity for authenticated users;
- settings link text is “Настройки” without gear icon;
- mobile navigation must be compact and ordered;
- logout remains available;
- admin panel link remains conditional.

#### user_cabinet
Purpose:
User cabinet, account block, learning block, settings.

Current state:
- `/cabinet` shows learning block above account block;
- `/cabinet/settings` exists for password change only;
- learning block has two columns:
  - course entry;
  - protected student project file download;
- learning block uses server-side access state.

#### auth
Purpose:
Login/register/logout/reset/password helpers.

Current state:
- password settings use existing hash/verify helpers;
- reset password flow must remain unchanged;
- payment is not implemented here yet.

#### materials
Purpose:
Learning/materials routes and course delivery.

Current state:
- course route `/materials/drafts/dair-smoke-20260529/`;
- course data and assets must be protected if they expose paid content;
- course access uses materials access helper;
- unpaid users must be blocked server-side.

#### protected learning file
Purpose:
Download student project file only for admin/materials-access users.

Rule:
Never serve the protected project file from public static and never expose GitHub raw URL in HTML.
