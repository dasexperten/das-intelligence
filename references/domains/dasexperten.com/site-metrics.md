# Site metrics — dasexperten.com

**Source of truth for numbers:** Ubersuggest (live MCP or app.neilpatel.com)  
**ERP cache:** KV key `seo:site:dasexperten.com` via `GET/POST /api/seo/site-metrics`

## Current snapshot (2026-08-24)

| Metric | Value | Notes |
|---|---|---|
| Domain authority | **10** | Ubersuggest DA (was 11 on 2026-07-13) |
| Backlinks | **1 163** | total |
| Referring domains | **351** | unique ref domains |
| Organic traffic (est.) | **149** / mo | Ubersuggest `traffic` = 2026-07 `searchTraffic` |
| Organic keywords | **86** | ranking set (en, loc often US/2840) |
| Follow / nofollow | 920 follow · 243 nofollow | domain overview |
| Paid traffic (est.) | 4 302 | July 2026 US paid estimate — not organic KPI |
| GSC linked in Ubersuggest | yes | `isConnectedToGSC: true` |
| GA linked in Ubersuggest | yes | `isConnectedToGA: true` |

### Organic traffic history (Ubersuggest `domainTraffic.searchTraffic`)

| Month | Organic traffic | Organic KW |
|---|---|---|
| 2025-10 | 0 | 2 |
| 2025-11 | 54 | 15 |
| 2025-12 | 753 | 18 |
| 2026-01 | 74 | 12 |
| 2026-02 | 65 | 15 |
| 2026-03 | 83 | 33 |
| 2026-04 | 131 | 28 |
| 2026-05 | 96 | 27 |
| 2026-06 | 124 | 17 |
| 2026-07 | **149** | **86** |

Spike Dec 2025 (753) then rebased lower — treat as tool volatility; confirm with GSC. August 2026 month not yet in the Ubersuggest series as of 2026-08-24.

### Sample organic keywords (en, position often deep)

| Keyword | Position | Volume | Path |
|---|---|---|---|
| probiotic toothpaste | 24 | 8100 | `/best/probiotic-toothpaste` |
| cuál es la mejor pasta dental para dientes sensibles | 12 | 50 | `/es/best/toothpaste-for-sensitive-teeth` |
| what is enzymatic toothpaste | 20 | 50 | `/learn/what-is-enzyme-toothpaste` |
| inocles | 20 | 110 | inocles blog |

Commercial head terms still sit deep; `probiotic toothpaste` is the first keyword in the 20s. Tool still lists some `/product-page/*` URLs.

## Seed used in ERP (Worker fallback when KV empty)

```json
{
  "domain": "dasexperten.com",
  "domain_authority": 11,
  "backlinks": 1093,
  "ref_domains": 328,
  "organic_traffic": 124,
  "source": "seed"
}
```

Live KV after 2026-08-24 POST (TTL ~30 days):

```json
{
  "domain": "dasexperten.com",
  "domain_authority": 10,
  "backlinks": 1163,
  "ref_domains": 351,
  "organic_traffic": 149,
  "updated_at": 1787560000,
  "source": "ubersuggest"
}
```

## History log

| Date | DA | Backlinks | Ref domains | Organic | Source |
|---|---|---|---|---|---|
| 2026-07-13 | 11 | 1093 | 328 | 124 | Ubersuggest MCP (domain_overview + backlinks_overview) |
| 2026-07-13 | 11 | 1093 | 328 | 124 | Ubersuggest MCP re-pulse → POST dasoperator-api `/api/seo/site-metrics` OK |
| 2026-07-16 | pending | pending | pending | pending | GEO-WEEK Day-0 pulse attempted; Ubersuggest MCP blocked (interactive approval unavailable in session) — last-known-good = 2026-07-13 row; re-pulse next agent session |
| 2026-07-16 | 11 | 1091 | 327 | 124 | Ubersuggest MCP domain_overview (real, GEO-week session). DA flat vs 07-13; BL 1093→1091, RD 328→327 (minor natural drift). follow 844 / nofollow 247. organic KW 17. ERP POST pending (dasoperator base URL/auth not in this session) |
| 2026-07-17 | 11 | 1091 | 327 | 124 | Ubersuggest MCP domain_overview + backlinks_overview (real). Flat vs 07-16 (weekly refresh cadence). nofollow 247. |
| 2026-08-24 | 10 | 1163 | 351 | 149 | Ubersuggest MCP → POST dasoperator-api `/api/seo/site-metrics` OK · was serving seed (`updated_at: 0`) |

Append a row on every refresh. Never overwrite old rows — append only.

**GEO-WEEK note (2026-07-16):** DA is a lagging Ubersuggest metric — no movement expected within days of the sprint. Week measures inputs (RD earned via outreach, citations, entity, internal links, schema). Backlinks/RD dipped 2/1 (natural churn), not a concern. Real +DA, if any, lands on Ubersuggest's own refresh cadence (weeks).
