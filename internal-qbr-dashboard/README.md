# Northstar Retail Group — Internal QBR Dashboard

Internal quarterly business review for the Northstar flagship support assistant,
covering 1–31 August 2026. Account health, trends over the period, operational
risks, the expansion picture, and the decisions that need making.

**Audience: internal account team.** This view contains commercial judgment that is
deliberately excluded from the customer-facing dashboard.

Every figure derives from `data/northstar_flagship_30_day_metrics.csv` — 31 rows,
one deployment, no imputation or adjustment.

## Project type

Static HTML / CSS / JavaScript. No framework, no build step, no dependencies,
no `npm install`. A single self-contained `index.html`: inline CSS, inline JS,
inline data, charts drawn as inline SVG by the page's own code. The only external
request is a Google Fonts stylesheet (Manrope, JetBrains Mono).

## Structure

```
.
├── index.html                                  the dashboard
├── data/northstar_flagship_30_day_metrics.csv  source data
└── README.md
```

## Deploying

Zero config. On Vercel: Framework Preset **Other**, Build Command **empty**,
Output Directory **empty**, no environment variables.

## Notes

- The page carries `<meta name="robots" content="noindex">`. Remove that line to
  allow search indexing.
- Navigation is three client-side panels (Account Health / Forward Focus /
  Additional Review) — no routing, so no rewrite rules are needed.
- If Google Fonts is unreachable the page falls back to the system stack declared
  in each `font-family`; metrics shift slightly, layout holds.
