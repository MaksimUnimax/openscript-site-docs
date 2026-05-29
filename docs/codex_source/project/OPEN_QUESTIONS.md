# Open questions

STATUS: INITIAL_FROM_CURRENT_REPO_DOCS

## OPEN_QUESTIONS_UPDATE_20260529_AI_STARTER_COMMUNITY

### OPEN_QUESTION_20260529_01 — Payment implementation

There is currently no proven payment transaction/order/subscription model and no proven payment success handler.

Needed later:
- define payment provider/flow;
- define tariff/access product;
- ensure successful payment sets permanent materials access;
- preserve separation between one-time materials access and future optional paid options.

### OPEN_QUESTION_20260529_02 — Admin access live mismatch

A previous report claimed admin learning access was fixed, but a later live screenshot still showed locked UI while admin navigation was visible. A follow-up prompt was generated to prove and fix admin access consistency.

Docs must record the rule:
If the user is admin for the header/admin panel, that same admin identity must unlock cabinet learning UI, course route and project file download.

### OPEN_QUESTION_20260529_03 — Final visual acceptance of learning block

Learning block visual style was iterated:
- “Обучающий блок” heading;
- two columns;
- centered bottom instruction;
- orange action buttons.

Final browser acceptance should be based on current live UI, not old screenshots.

### OPEN_QUESTION_20260529_04 — Complete docs refinement

Several canonical docs may not yet exist or may still contain Agent Lab wording. Need a refinement pass after this memory update.
