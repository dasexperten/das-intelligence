# EMAILER SKILL MIRROR

**SSOT:** [dasexperten/das-architektura](https://github.com/dasexperten/das-architektura) → `SKILLS/emailer/`

This directory is a **copy** for local agent loaders. When rules conflict, **architektura wins**.

**Hard rules (Owner):**
1. Outbound corporate email = **this emailer skill only** (Resend + ALLOWED_FROM).
2. **emailer ≠ sales-hunter.** Not connected.
3. **sales-hunter** runs **only** when Owner asks for sales-hunter **by name**. Never auto-run for send/XA/GEO/cron.
4. Secrets: `SECRETS/resend.md` in **das-architektura** (or org mirror) — do not invent keys.

Last synced from architektura: see git history of this folder.
