# Ubersuggest — pull & refresh protocol

## When to use

- Daily / weekly domain pulse for dasexperten.com  
- Before SEO board reviews  
- After major content, PR, or backlink campaigns  
- Whenever ERP home SEO cards look stale  

## MCP tools (Grok / connected agents)

| Tool | Use for |
|---|---|
| `ubersuggest__domain_overview` | DA, traffic, organic KW count, keyword sample, traffic history |
| `ubersuggest__backlinks_overview` | DA, backlinks, ref domains, follow/nofollow |
| `ubersuggest__backlinks` | individual links (outreach / toxic review) |
| `ubersuggest__domain_keywords` | full organic/paid KW list |
| `ubersuggest__domain_top_pages` | top pages by est. traffic |
| `ubersuggest__backlink_opportunity` | competitor ref domains we lack |
| `ubersuggest__pagespeed_audit` | CWV / PageSpeed |
| `ubersuggest__traffic_value` | $ traffic value |

Example:

```text
domain_overview domain=dasexperten.com language=en
backlinks_overview domain=dasexperten.com
```

## Refresh ERP (mandatory after pull)

```http
POST https://erp.dasexperten.com/api/seo/site-metrics
Content-Type: application/json

{
  "domain": "dasexperten.com",
  "domain_authority": 11,
  "backlinks": 1093,
  "ref_domains": 328,
  "organic_traffic": 124
}
```

- Sets `source: "ubersuggest"` and `updated_at` (unix seconds).  
- KV TTL ~30 days.  
- Auth: same ERP session / worker auth as other write routes.

## Update this repo

1. Append row to `site-metrics.md` history table.  
2. Update “Current snapshot” numbers.  
3. Optional: note keyword shifts if top-10 set changed.

## Skill

Run `skills/seo/ubersuggest-site-pulse` for the full checklist.
