# Measurement sources — dasexperten.com

| System | Role | Wire status 2026-07-13 |
|---|---|---|
| **Ubersuggest** | DA, backlinks, ref domains, est. organic traffic/KW | Live via Grok MCP; ERP KV snapshot |
| **Google Search Console** | queries, clicks, CTR, index | Linked in Ubersuggest; full GSC API in ERP pending verification |
| **GA4** `511756146` | sessions, AI referrers, conversions | Ready for Data API |
| **Yandex Metrika** | RU organic phrases (Traffic tab) | Live in analytics UI |
| **Microsoft Clarity** | heatmaps, AI Visibility UI | Live product; export TBD |
| **Cloudflare AI Crawl Control** | bot allow/block stats | Blocked until zone feed / NS |
| **Cloudflare Pages** | erp.dasexperten.com deploy | Live |

## Contours

- **Global storefront SEO** → this dossier + Ubersuggest + GSC.  
- **RU marketplace / Metrika** → dasoperator analytics Traffic tab (not DA).  
- **ERP internal UI** → deSIGNER / Design mobile-ui (not SEO metrics).  

## Forbidden

- Hard-coded vanity metrics in UI.  
- Mixing paid traffic estimate into “Organic traffic” KPI.  
- Claiming CF AI crawler numbers without API.  
