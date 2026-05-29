# App module map

STATUS: CURRENT_OPENSCRIPT_SITE_MEMORY

This is the current app-side module map summary for OpenScript site work.

Verified app repo reference:
- `/opt/ai-starter-community`

Verified app branch for the current memory snapshot:
- `design/product-story-03`

Verified cleanup commit for the active skill inventory:
- `24d518fdb3a09babb4a32492706975a3f6165a06`

Likely next app areas to re-prove before implementation:
- `app/materials`
- `app/user_cabinet`
- `app/auth`
- `app/payments`
- `app/admin`

Tooling and skills area:
- `.agents/skills/**` contains the clean exact-copy active skills copied into the app repo
- these files are tooling assets, not runtime state

Current caution:
- do not infer exact module implementation until a read-only app proof run
- do not confuse the site app with Agent Lab, APM, Telegram/VK, or OpenDesign Lab

Boundary reminder:
- course content should eventually be git-tracked app source
- runtime state is not source-of-truth
