
# Telecel Marketplace – Weekly Trends Dashboard (JSON + Tooltips)

This version of the weekly trends dashboard:

- Loads its data from **`weekly-data.json`** (no database or backend).
- Shows **tooltips on hover** for every chart data point (week, metric name, value, and period).
- Keeps the same dark Telecel dashboard theme.

## Files

- `index.html` – self-contained HTML, CSS and JavaScript for the dashboard UI and charts.
- `weekly-data.json` – weekly aggregate metrics. Edit this file to update the dashboard.

## Updating the data

1. Open `weekly-data.json` in your editor or directly in GitHub.
2. For each week object under `weeks`, adjust the numbers or add/remove weeks as needed:
   - `labelShort` – short label used on the X-axis (e.g. `"W6"`).
   - `period` – human-readable label (e.g. `"Week 6 (Nov 19–23)"`).
   - `totalTransactions`, `successfulTransactions`, `gmv`, `aov`,
     `highestOrder`, `cashback`, `totalUsers`, `uniqueUsers`.
3. Commit the changes — your static host (e.g. Cloudflare Pages) will redeploy automatically,
   and the dashboard will reflect the new data.

## Deploy on GitHub + Cloudflare Pages

1. Create a new GitHub repo (e.g. `telecel-weekly-trends-dashboard`).
2. Add both `index.html` and `weekly-data.json` to the **root** of the repo and commit.
3. In Cloudflare Dashboard → **Pages** → **Create a project** → **Connect to Git**.
4. Select this repo and configure:
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Output directory: `/`
5. Deploy — the site will be live at `https://<project>.pages.dev`.

Hover over any dot on a chart to see the exact value and its week/period.
