# Ubersuggest Site Pulse

## Purpose

Pull live domain authority, backlinks, referring domains, and organic traffic from Ubersuggest, update the dasexperten.com dossier, and refresh the Das Operator ERP cache.

## When to Use

- Daily/weekly domain pulse  
- Before SEO reviews or DA scout loops  
- After content / PR / backlink campaigns  
- When ERP home SEO cards look stale or show `seed`  

## When NOT to Use

- Full technical crawl → `technical-seo-auditor`  
- GSC query mining → `search-console-expert`  
- GEO/AI content structure → `geo-ai-visibility` / `ai-seo-optimizer`  

## Inputs

- Domain (default `dasexperten.com`)  
- Optional: language / locId for keyword context  
- Access to Ubersuggest MCP or app export  

## Workflow

1. Call `ubersuggest__domain_overview` and `ubersuggest__backlinks_overview`.  
2. Extract: domainAuthority, backlinks, refDomains, traffic (organic), organic keyword count.  
3. **Never invent numbers.** If MCP fails, say so and keep last known good.  
4. POST metrics to ERP `/api/seo/site-metrics` (see `references/domains/dasexperten.com/erp-wire.md`).  
5. Append a history row in `references/domains/dasexperten.com/site-metrics.md`.  
6. Summarize MoM organic traffic from `domainTraffic` if present.  
7. Flag anomalies (e.g. traffic spike without GSC confirmation).  

## Output

Always provide:

- KPI table (DA, backlinks, ref domains, organic traffic, organic KW)  
- Source + pull timestamp  
- ERP refresh status (posted / failed / skipped)  
- Dossier update status  
- Optional: top keyword positions worth action  
- Next checkpoint date  

## Common Mistakes

- Using paid traffic as organic KPI  
- Skipping ERP POST after a successful pull  
- Overwriting history instead of appending  
- Shipping fake dashboard numbers when MCP is down  

## Related

- Domain dossier: `references/domains/dasexperten.com/`  
- `seo-performance-monitor`, `geo-ai-visibility`, `seo-audit-expert`  
