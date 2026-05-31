# Staging proof — OpenScript / AI Starter Community

STATUS: PROVEN_RUNTIME
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-staging-health-proof-20260531
DATE: 2026-05-31

## What is proven

1. **Staging support files exist.**
   - /opt/ai-starter-community/staging/start.sh
   - /opt/ai-starter-community/staging/env.staging.example
   - /opt/ai-starter-community/staging/README.md
   - /opt/ai-starter-community/staging/data/.gitkeep
   - /opt/ai-starter-community/staging/runtime/.gitkeep

2. **.gitignore protects staging runtime/data.**
   - staging/data/* is ignored (except .gitkeep)
   - staging/runtime/* is ignored (except .gitkeep)
   - staging scripts and README are tracked in git

3. **No core application source code was modified.**
   - source/app/** is unchanged
   - source/tests/** is unchanged

4. **Staging is isolated from production.**
   - Separate port: 8090 vs production default 8089
   - Separate database path
   - Separate session cookie name
   - localhost-only bind
   - No production SMTP credentials
   - No production .env access

5. **start.sh syntax is valid.**
   - bash -n passes without errors

6. **Staging runtime health proven.**
   - Staging started on 127.0.0.1:8090
   - Listener confirmed: only 127.0.0.1:8090
   - /healthz returned: {"ok":true,"service":"ai-starter-community"}
   - /readyz returned: {"ok":true,"ready":true}
   - Process stopped after health check
   - Port 8090 confirmed free after stop

7. **start.sh uses project virtual environment.**
   - source/.venv/bin/python is used when available
   - Fix was needed and committed

8. **Agent Lab repos were not touched.**

## Runtime paths touched (staging-only)

- /opt/ai-starter-community/staging/data/ — SQLite database was created
- /opt/ai-starter-community/staging/runtime/ — health-proof.log was written
- Both paths are gitignored and safe to delete
