# Codex Run Rules

## Before every run

Codex must know:
- task type;
- exact scope;
- exact docs to read;
- allowed files/directories;
- forbidden files/directories;
- validation expectations;
- report format.

## Run classes

PROOF_ONLY:
- read-only;
- no changes;
- no commit;
- no push.

DESIGN_ONLY:
- documentation/design only;
- no implementation code.

DOCS_ONLY:
- documentation changes only.

IMPLEMENTATION:
- code changes allowed only in explicit scope;
- validation required.

## STOP conditions

Codex must stop if:
- secrets are required;
- docs are missing;
- repo state is dirty outside scope;
- task requires unrelated project;
- remote is missing for push;
- command may expose credentials;
- facts are insufficient.

