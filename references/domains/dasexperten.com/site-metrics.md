# Site metrics — dasexperten.com

**Source of truth for numbers:** Ubersuggest (live MCP or app.neilpatel.com)  
**ERP cache:** KV key `seo:site:dasexperten.com` via `GET/POST /api/seo/site-metrics`

## Current snapshot (2026-07-13)

| Metric | Value | Notes |
|---|---|---|
| Domain authority | **11** | Ubersuggest DA |
| Backlinks | **1 093** | total |
| Referring domains | **328** | unique ref domains |
| Organic traffic (est.) | **124** / mo | Ubersuggest `traffic` |
| Organic keywords | **17** | ranking set (en, loc often US/2840) |
| Follow / nofollow | 844 follow · 249 nofollow | domain overview |
| Paid traffic (est.) | ~31 416 | US paid estimate — not organic KPI |
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
| 2026-06 | **124** | 17 |

Spike Dec 2025 (753) then rebased lower — treat as tool volatility; confirm with GSC.

### Sample organic keywords (en, position often deep)

| Keyword | Position | Volume | Path |
|---|---|---|---|
| hemp toothpaste | 33 | 70 | coconut-hemp product |
| toothpaste black | 51 | 70 | charcoal product |
| nano brush toothbrush | 54 | 210 | nano-massage brush |
| black charcoal toothpaste | 60 | 390 | charcoal product |
| silicone bristle toothbrush | 62 | 170 | nano-massage brush |

Most commercial queries sit positions 50–100 — growth lever is content + internal links + backlinks, not paid alone.

## Seed used in ERP (until KV refresh)

```json
{
  "domain": "dasexperten.com",
  "domain_authority": 11,
  "backlinks": 1093,
  "ref_domains": 328,
  "organic_traffic": 124,
  "source": "ubersuggest"
}
```

## History log

| Date | DA | Backlinks | Ref domains | Organic | Source |
|---|---|---|---|---|---|
| 2026-07-13 | 11 | 1093 | 328 | 124 | Ubersuggest MCP (domain_overview + backlinks_overview) |
| 2026-07-13 | 11 | 1093 | 328 | 124 | Ubersuggest MCP re-pulse → POST dasoperator-api `/api/seo/site-metrics` OK |

Append a row on every refresh. Never overwrite old rows — append only.
