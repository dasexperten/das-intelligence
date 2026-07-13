# GEO / AI visibility — dasexperten.com

**GEO** = Generative Engine Optimization (AI answer engines, LLM citations, bot crawl).  
**Not** geo-IP pricing (that lives in storefront code).

## Goals

1. Be crawlable by major AI bots (with intentional allow/deny policy).  
2. Be citable: clear entities, FAQs, proof, schema.  
3. Track referrals from AI products when available.  
4. Surface status on Das Operator home (das-dashboard pattern) — **real data only**.

## Data sources (status 2026-07-13)

| Signal | Source | Status |
|---|---|---|
| AI crawler requests / allow rate | Cloudflare AI Crawl Control | **Blocked** until NS-flip fully exposes zone stats API |
| Traffic from AI referrers | GA4 property `511756146` | Ready (filter AI sources) |
| Citations / share of authority | Microsoft Clarity AI Visibility | Live in Clarity UI; export path TBD |
| Google Search / AI Overviews | GSC | Site verification pending for some properties |
| Site authority (classic SEO) | Ubersuggest | **Live** — see site-metrics.md |

## AI Crawlers UI (ERP)

- Pattern: `Design/das-dashboard.md` (deSIGNER SYSTEM + dasoperator Design).  
- Component: `dasoperator/web/components/home/ai-crawlers.tsx` — still **demo payload** until CF feed is wired.  
- Must show `· demo data` when not live (rule in das-dashboard).  
- **Do not** invent crawler counts.

## Operator home

| Block | Data |
|---|---|
| SEO KPI strip (4 cards) | Real Ubersuggest via `/api/seo/site-metrics` |
| Site authority panel | Same |
| AI Crawlers panel | Demo until CF |

## Playbook (GEO)

1. Entity consistency: brand, products, claims, INCI — match packaging/tech SSOT.  
2. Answer-first pages: FAQ, science, comparison with proof.  
3. Schema: Product, FAQ, Organization, Breadcrumb.  
4. `llms.txt` / robots policy for AI bots — deliberate, not accidental block.  
5. Monitor AI bot hits after CF AI Crawl Control is available.  
6. Outreach via `partnerships@` as collaboration, never “link building” language.

## Skills

- `skills/seo/geo-ai-visibility`  
- `skills/seo/ai-seo-optimizer`  
- `skills/seo/schema-markup-specialist`  
- `skills/website/microsoft-clarity-analyst`  
