# Measurement sources — dasexperten.com

| System | Role | Wire status 2026-07-13 |
|---|---|---|
| **Ubersuggest** | DA, backlinks, ref domains, est. organic traffic/KW | Live via Grok MCP; ERP KV snapshot |
| **Google Search Console** | queries, clicks, CTR, index | Linked in Ubersuggest; full GSC API in ERP pending verification |
| **GA4** `511756146` | sessions, channels, landings, funnel, revenue | LIVE Data API in ERP (`/api/ga4/*`); vault `SECRETS/google-analytics-ga4.md` + hub `web-analytics.md` |
| **Yandex Metrika** `107720199` | RU organic phrases, sources, bounce/duration | LIVE (`/api/metrika/*`); vault `SECRETS/yandex-metrika.md` |
| **Microsoft Clarity** | dead/rage/quickback, scroll, device/geo, recordings UI | LIVE Export API (`/api/clarity/*`, 10/day); vault `SECRETS/microsoft-clarity.md` |
| **Cloudflare AI Crawl Control** | bot allow/block stats | Blocked until zone feed / NS |
| **Cloudflare Pages** | erp.dasexperten.com deploy | Live |

**Credential vault (not in this repo):** `dasexperten.com/SECRETS/web-analytics.md`.

## Contours

- **Global storefront SEO** → this dossier + Ubersuggest + GSC.  
- **RU search intelligence** → Metrika Traffic tab (not DA).  
- **Behavior / UX** → Clarity Behavior tab + Clarity web UI.  
- **ERP internal UI chrome** → deSIGNER (not metrics).  

## Forbidden

- Hard-coded vanity metrics in UI.  
- Mixing paid traffic estimate into “Organic traffic” KPI.  
- Claiming CF AI crawler numbers without API.  
- Blending GA4 + Clarity + Metrika into one number without a labelled formula.  
