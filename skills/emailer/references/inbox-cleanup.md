# INBOX CLEANUP MODE

Mass deletion of threads (newsletters, promo, system notifications). Different from send mode but uses the same Worker / Apps Script bridge.

This file is loaded on demand from SKILL.md when any of these triggers fire:
- "удали все письма от X", "почисти ящик от Y", "delete all from X", "убери в трэш"
- "найди и удали", "сноси рассылки", "clean inbox of"
- "какие у меня рассылки?", "what newsletters do I have?"

---

## 1. ABSOLUTE SAFETY GATE — non-negotiable

Same principle as send-gate (SKILL.md Section 0): never trash without explicit confirmation. Trash auto-purges after 30 days = irreversible.

**Before EVERY `trash_threads` call:**
1. Show full list: count, dates, subjects, senders, thread_ids in compact table
2. Flag any thread with `message_count > 1` as `⚠️ DIALOG` — these are real conversations, not blast mail
3. Output: `Подтверди удаление: "ок" / "шли в трэш" / "удаляй"`
4. STOP. Wait for next user message. Same accept-words as send confirmation
5. If user says "да"/"ок" after a multi-option question — re-ask which option. Never guess
6. If user says "всё это" or "всё" after a grouped list — re-ask which group(s)

---

## 2. SEARCH PATTERNS (find action)

Three rules that prevent silent under-counting:

**1. Always use `in:anywhere`** — without it, archived/Promotions/Spam are hidden. Inbox-only search returned 6 Ozon threads where 11 actually existed.

**2. Search by top-level domain, not exact email.** `from:oborot.ru` catches both `news-flash@oborot.ru` AND `news-flash@news.oborot.ru`. Searching `@news.oborot.ru` misses bare-domain variant; `@oborot.ru` (with @) misses subdomains. Always: `from:domain.tld`.

**3. `max_results: 500` is a lie — backend caps at 50 per call.** For >50 threads paginate by date cuts:
```
newer_than:30d
newer_than:90d older_than:30d
newer_than:180d older_than:90d
newer_than:1y older_than:180d
newer_than:2y older_than:1y
older_than:2y
```
Dedupe by `thread_id` across batches. Stop expanding when a new cut returns 0 new ids.

---

## 3. NEWSLETTER DISCOVERY PATTERN

When user asks "какие у меня рассылки?":

1. Pull a sample across the last 2 years (≥250 threads via date cuts above)
2. Group by sender email (extract from `<...>` with regex)
3. Filter senders matching: `noreply`, `no-reply`, `news`, `newsletter`, `info@`, `marketing`, `promo`, `mailer`, `mailing`, `digest`, `do-not-reply`
4. Show top senders ≥2 threads, with subject samples
5. Classify into:
   - **Pure newsletter** — safe to mass-trash (cantonfair, oborot, ozon promo, exportcenter, payoneer marketing)
   - **Gray zone** — see Section 6 below
6. Present groups separately. Never offer to bulk-delete the gray zone — present those individually for user judgment.

---

## 4. TRASH BATCHING

`trash_threads` accepts arrays. Backend handles 50/call comfortably. For >50 ids, chunk:

```python
for i in range(0, len(ids), 50):
    chunk = ids[i:i+50]
    curl --max-time 60 -X POST <worker> -d '{"action":"trash_threads","thread_ids":chunk}'
```

Report per-batch: `trashed X/Y, failed N`. Never silently swallow failures.

---

## 5. RESURRECTION VIA FORWARDING

If `eurasia@dasexperten.com` (or any other corporate alias) forwards back to `dasexperten@gmail.com`, trashed threads can reappear as fresh threads with new IDs after the next forward cycle. Symptom: `trashed: 121, failed: 0`, then `find` 5 minutes later shows the threads alive again.

**This is not a tool failure.** Trash worked. The forwarder re-injected.

Fix at source, not in Gmail:
- **Option A** — open one such thread, click `Unsubscribe` in footer (1 minute, surgical)
- **Option B** — Gmail filter rule via Apps Script: `from:domain.tld → trashed` (catches future inflow auto)

Inform Aram of resurrection cause in the final summary, do not retry trash.

---

## 6. GRAY ZONE — DO NOT MASS-DELETE WITHOUT REVIEW

Senders that look like newsletters but carry transactional or operational value:

| Sender pattern | Why dangerous |
|---|---|
| `info@business.vtb.ru`, `mybank@byblosbank.am`, `vietinbank-efast@vietinbank.vn` | Bank statements, payment confirmations, security alerts |
| `noreply-oplata@cdek.ru`, `finance@pay.yandex.ru` | Payment receipts, refund notices |
| `sellersupport@shop.tiktok.com` | Active appeal threads — DasExpertenVN appeal context applies |
| `marketplace@seller.ozon.ru` | Mix of promo AND transactional (acceptance, returns, statements) — split by subject only |
| `googlebase-noreply@google.com` | Merchant Center disapprovals — affects active listings |
| `notifications@github.com` | Active CI / PR / security alerts |
| `info@make.com` | Scenario failure alerts |

For these — never bulk. Always: filter by subject, present individually, get per-subject confirmation.

---

## 7. AVAILABLE ACTIONS BEYOND SEND/TRASH

Apps Script Web App also exposes (use directly via curl to Worker):
- `find` — Gmail search, returns thread metadata
- `get_thread` — full thread content by thread_id
- `archive` — move to Archive (no trash)
- `trash_threads` — move to Trash (30-day auto-purge)
- `apply_label` — tag threads with custom labels
- `create_filter` — create Gmail filter rule (domain-level auto-actions)

For filter creation (Resurrection fix Option B), use `create_filter` with criteria `from:domain.tld` and action `addLabelIds: ["TRASH"]`.

---

## 8. STANDARD WORKFLOW

```
1. Aram: "удали все письма от X"
2. emailer: paginate find → collect thread_ids
3. emailer: classify (newsletter / gray / dialog)
4. emailer: display table + count → wait
5. Aram: "ок"
6. emailer: trash_threads in batches of 50 → report
7. emailer: if subsequent find still shows threads → flag forwarding loop
```

---

## 9. CHANGE LOG

- **2026-05-01** — initial reference. Captured from live session: 383 threads trashed across Rutube / Ozon promo / oborot.ru / Честный ЗНАК support / 9 newsletter senders. Patterns extracted: pagination cap, `in:anywhere` rule, domain-vs-subdomain search trap, gray-zone classification, resurrection-via-forwarding pattern.
