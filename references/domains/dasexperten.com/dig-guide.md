# Dig guide — interesting data (no secrets)

**Credentials live in** `dasexperten.com/SECRETS/web-analytics.md` (hub) + child files.  
**Safe place to explore:** ERP → `/analytics` (cached, multi-source labelled).

## Contours (do not blend)

| Tracker | Contour | Rough character |
|---|---|---|
| GA4 `511756146` | Global `.com` | Often **paid-heavy** |
| Clarity | Global behavior | Often **VN mobile-heavy** |
| Metrika `107720199` | **RU** | Query phrases goldmine, low volume |

## High-value digs

### 1. RU SEO content ideas → Metrika
- Top search phrases 30d (`/api/metrika/phrases`)
- Money clusters without landings (enzyme / probiotic / charcoal / fluoride-free / braces) — already flagged in Traffic tab

### 2. Paid efficiency vs landings → GA4
- Channels: paid share, organic thinness
- Landing pages: traffic without purchase
- Funnel: which step loses people

### 3. UX friction → Clarity
- Dead / rage / quickback %
- Scroll depth vs page length
- Recordings + heatmaps in Clarity **web UI**
- AI Visibility panel in Clarity UI (citations) — not yet ERP-wired

### 4. Authority (classic SEO) → Ubersuggest
- Separate dossier: `site-metrics.md` (DA / backlinks / organic est.)
- Not a substitute for GA sessions

### 5. Nightly archive → D1
- `web_analytics_daily` — GA4 + Metrika day grains
- `web_behavior_snapshots` — Clarity history (only after cron started; no backfill)

## Quota caution

Clarity Export API: **10 calls/project/day**. Nightly uses 1. Prefer ERP Behavior + history endpoints.

## Related

- Secrets hub: `SECRETS/web-analytics.md`
- Metric map: `dasoperator/docs/analytics-parity.md`
