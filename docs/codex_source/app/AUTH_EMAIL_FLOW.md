# Auth and Email Flow

Known requirements:
- registration by email;
- email verification;
- login by email or login;
- password reset by email;
- SMTP delivery configured in previous work;
- secrets must never be printed or committed.

Known prior issue:
Password reset emails were rejected when BASE_URL used raw IP/port.
Domain + HTTPS solved it.

Current exact implementation must be verified before auth/email changes.

