# Marketplace Skills

This folder contains practical marketplace skills for listing optimization, search visibility, images, video, reviews, questions, pricing, ads, ranking, competitor analysis, launches, analytics, promotions, content review, and account health.

## Structure

The current Marketplace foundation uses shared skills to avoid duplicating the same logic across every platform.

```text
skills/marketplaces/shared/skill-name/
├── SKILL.md
├── templates.md
└── checklist.md
```

Platform folders can later add local rules, platform-specific terms, and advanced playbooks.

## Completed Shared Marketplace Skills

1. `marketplace-listing-optimizer`
2. `marketplace-seo-expert`
3. `marketplace-image-expert`
4. `marketplace-video-expert`
5. `marketplace-reviews-expert`
6. `marketplace-questions-expert`
7. `marketplace-pricing-expert`
8. `marketplace-ads-expert`
9. `marketplace-ranking-expert`
10. `marketplace-competitor-analyst`
11. `marketplace-launch-manager`
12. `marketplace-analytics-expert`
13. `marketplace-promotion-planner`
14. `marketplace-content-auditor`
15. `marketplace-account-health-monitor`

## Platform Folders

- `wildberries/`
- `ozon/`
- `amazon/`
- `shopee/`
- `lazada/`
- `tiktok-shop/`
- `noon/`

## Usage Logic

Use shared skills first:

- content issue → `marketplace-listing-optimizer` or `marketplace-content-auditor`
- search issue → `marketplace-seo-expert`
- image issue → `marketplace-image-expert`
- video issue → `marketplace-video-expert`
- review issue → `marketplace-reviews-expert`
- question issue → `marketplace-questions-expert`
- price issue → `marketplace-pricing-expert`
- ads issue → `marketplace-ads-expert`
- ranking issue → `marketplace-ranking-expert`
- competitor issue → `marketplace-competitor-analyst`
- launch issue → `marketplace-launch-manager`
- performance issue → `marketplace-analytics-expert`
- promotion issue → `marketplace-promotion-planner`
- account risk issue → `marketplace-account-health-monitor`

## Status

Marketplace foundation is complete for the current KISS stage.

Next category: SEO skills or platform-specific deep packs for Wildberries, Ozon, TikTok Shop, Amazon, Shopee, Lazada, and Noon.
