# Account blocks

STATUS: CURRENT
PROJECT: OpenScript / AI Starter Community

## Purpose

The `account_blocks` feature provides server-backed cabinet blocks for account credentials and activation state.

## Source-backed implementation

- Backend service: `app/account_blocks/`
- Cabinet surface: `app/user_cabinet/`
- Admin surface for moderator assignment: `app/admin/`
- Shared DB support: `app/shared/db.py`
- Activation email: `app/notifications/`

## Schema summary

Proven `account_blocks` columns:
- `id`
- `owner_user_id`
- `type`
- `title`
- `login`
- `password_secret`
- `email`
- `status`
- `duration_days`
- `activated_at`
- `expires_at`
- `created_by_user_id`
- `updated_by_user_id`
- `activated_by_user_id`
- `created_at`
- `updated_at`

## Supported block types

- `chatgpt` → `ChatGPT`
- `server` → `Сервер`
- `mail` → `Почта`
- `vpn` → `ВПН`

## UI rules

- The cabinet is server-backed; localStorage is not the source of truth for account blocks.
- Owner is resolved server-side and hidden from the visible block UI.
- Manual title and manual email inputs are not part of the visible block UI.
- Visible copy fields are login and password for regular account blocks; VPN does not require credential fields.
- Admin and moderator can create, edit, delete, and activate blocks.
- Normal users are copy-only.
- Delete and activate are real protected POST actions.
- Latest no-jump behavior is implemented with fetch-based form handling and scroll preservation.
- Account cards use bounded width and do not stretch full width on desktop/tablet when only one card exists.
- The restored cabinet grid remains 4 columns desktop / 2 tablet / 1 mobile.

## Activation rules

- Activation starts the internal 60-day timer.
- Reactivation resets the timer.
- Visible wording uses elapsed-day status text.
- Inactive text is `Не активирован`.
- Active text is `Активен: день N`.
- Finished text is `Срок завершён`.
- Visible UI must not show `из 60` or `60 дней` for the account-block timer.

## Activation email

- Activation uses the owner user's registered email address.
- Subject: `Активирована опция OpenScript`
- Body includes the option name and links to:
  - `https://openscript.ru/`
  - `https://openscript.ru/cabinet`
- Activation email is sent/queued only on activate/reactivate.
- Create/update/delete do not send the activation email.
- Login and password are not included in the email body.

## VPN block notes

- VPN is a real server-backed account-block type, not a hardcoded cabinet card.
- VPN create/activate/renew/delete lifecycle exists alongside the other account blocks.
- VPN does not require login/password fields.
- The cabinet can render VPN content without credential inputs.
- VPN video source: `/static/videos/amnezia-vpn-guide.mp4`.
- The polished VPN panel in the reported feature/live-synced state includes Tech Talk attribution and a normal-sized Amnezia VPN button.
- The requested separate collapsible VPN block after Accounts is pending/not yet proven unless a later report confirms it.

## Security and limitations

- `password_secret` is stored as a service-isolated text field in the current implementation.
- Password-secret encryption or alternative secret storage policy is still open.
- Manual browser verification of the latest live no-jump/card-width/email behavior is still pending unless explicitly confirmed by the user.

## 2026-06-17 — P0 auth hardening source fix accepted

- The P0 auth hardening source fix completed in app commit `80b8d44d28c21bf5e22cf1674e04c6f5bedcf95b` did not change account-block storage semantics.
- `password_secret` remains a service-isolated text field in the current implementation.
- Password-secret encryption or an alternate secret-storage policy remains open.
- The next safe docs run for that topic should be a design/proof run with a DB/state backup gate before any migration or runtime mutation.
