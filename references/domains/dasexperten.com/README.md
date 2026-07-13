# Domain intelligence — dasexperten.com

**Status:** Canonical domain dossier for SEO / GEO / authority metrics  
**Owner domain:** `dasexperten.com` (primary storefront)  
**Related:** `dasexperten.de` (legacy; outbound mail from `.de` is dead — use `.com` only)  
**Last metrics pull:** 2026-07-13 via Ubersuggest MCP (Grok)

## What lives here

| File | Purpose |
|---|---|
| [site-metrics.md](./site-metrics.md) | Current DA / backlinks / organic traffic snapshot + history |
| [ubersuggest.md](./ubersuggest.md) | How to pull & refresh metrics (MCP tools, ERP wire) |
| [geo-ai-visibility.md](./geo-ai-visibility.md) | GEO / AI search / AI crawlers status |
| [erp-wire.md](./erp-wire.md) | Das Operator `/api/seo/site-metrics` contract |
| [sources.md](./sources.md) | GSC, GA4, Clarity, CF AI Crawl Control wiring status |

## Skills to run against this domain

| Task | Skill |
|---|---|
| Full SEO health | `skills/seo/seo-audit-expert` |
| Technical / crawl | `skills/seo/technical-seo-auditor`, `indexation-crawlability-auditor` |
| Ubersuggest pulse + ERP push | `skills/seo/ubersuggest-site-pulse` |
| GEO / AI answer engines | `skills/seo/geo-ai-visibility`, `ai-seo-optimizer` |
| GSC analysis | `skills/website/search-console-expert` |
| Performance report | `skills/seo/seo-performance-monitor` |
| Outreach mail (no “SEO” wording) | `seo-master` → emailer `partnerships@` (dasoperator SKILLS) |

## Hard rules

1. **Numbers only from real sources** — Ubersuggest, GSC, GA4, CF. Never invent DA / backlinks / traffic.
2. **Fake demo metrics are forbidden** on dashboards (removed 2026-07-13: DA 26 / linking 164 / backlinks 412).
3. **ERP shows KV snapshot** — refresh via `POST /api/seo/site-metrics` after each Ubersuggest pull.
4. **Outreach:** never say “SEO / backlink / link building” in external mail body (`partnerships@` persona).

## Live ERP surface

- Home Pulse SEO cards: Domain authority · Backlinks · Referring domains · Organic traffic  
- Site authority panel: same metrics, `source: ubersuggest|seed`  
- Implementation: `dasoperator` → `api/src/routes/seo.ts`, `web/components/home/*`
