# ERP wire — Das Operator SEO metrics

**Repo:** `dasexperten/dasoperator`  
**Route file:** `api/src/routes/seo.ts`  
**Mount:** `/api/seo`  
**UI:** home Pulse cards + Site authority panel  

## Contract

### `GET /api/seo/site-metrics?domain=dasexperten.com`

Returns:

```ts
{
  domain: string
  domain_authority: number
  backlinks: number
  ref_domains: number
  organic_traffic: number
  updated_at: number   // unix seconds
  source: 'ubersuggest' | 'seed'
}
```

- Reads KV `seo:site:{domain}` (default domain → `seo:site:dasexperten.com`).  
- Empty KV → seed constants (same numbers as last known good), persists seed.  

### `POST /api/seo/site-metrics`

Body fields: `domain?`, `domain_authority`, `backlinks`, `ref_domains`, `organic_traffic`.  
Always stores `source: 'ubersuggest'`.  

## Client

```ts
// web/lib/api.ts
getSiteSeoMetrics(domain = 'dasexperten.com')
```

## UI rules

- Labels stay: Domain authority · Backlinks · Referring domains · Organic traffic.  
- Design unchanged (4-card strip) — numbers only.  
- No fake AI Visibility metrics (DA 26 etc. removed 2026-07-13).  

## Agents

After any Ubersuggest pull, **POST** here and update  
`references/domains/dasexperten.com/site-metrics.md`.  
