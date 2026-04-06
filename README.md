# 📊 Subscription Cohort Retention Dashboard

An interactive post-upgrade cohort analysis dashboard tracking activation, engagement, transactions, and revenue across subscription plan tiers — built as a portfolio project.

🔗 **[Live Demo](https://YOUR-USERNAME.github.io/subscription-cohort-dashboard/cohort_dashboard_sample.html)**  
🌐 **[Portfolio Page](https://YOUR-USERNAME.github.io/subscription-cohort-dashboard/)**

---

## Overview

This project analyses how customers behave after upgrading their subscription plan, tracking whether they stay active, transact, and generate revenue over M0–M6 post-upgrade. The dashboard uses a heatmap-style cohort view to make retention patterns immediately readable across plan segments and time periods.

| | |
|---|---|
| **Data** | 9,802 rows · 7 filter dimensions · anonymised sample |
| **Time grain** | Monthly cohorts · Aug '25 → Mar '26 MTD |
| **Tech** | Pure HTML/CSS/JS · zero dependencies · works offline |

---

## Features

- **5 KPI cards** — Base, Active Rate, BC Active %, 3+ Day Active %, MTD GMV  
- **5 metric tabs** — Activation / BC Activation / 3+ Day Active / Transactions / GMV  
- **Cohort heatmap** — heat-scaled per column, dashed outline for partial MTD  
- **7 sidebar filters** — Plan Tier, Usage Band, Prior Status, Channel, Upgrade Type, Onboard Status, Engagement Tag  
- **Self-contained HTML** — no server, no build step, works offline  

---

## Files

| File | Description |
|---|---|
| `index.html` | Portfolio landing page (GitHub Pages home) |
| `cohort_dashboard_sample.html` | Full interactive dashboard |
| `cohort_dashboard_sample_data.csv` | Anonymised sample dataset |

---

## Quickstart

```bash
git clone https://github.com/YOUR-USERNAME/subscription-cohort-dashboard
cd subscription-cohort-dashboard
open cohort_dashboard_sample.html   # macOS
# or just double-click the file in Finder / Explorer
```

---

## Data Schema

One row per unique combination of cohort month + dimension filters.

| Column | Description |
|---|---|
| `month` | Cohort period — M1–M7, LMTD, MTD |
| `plan_tier` | Plan name e.g. S-Basic, D-Standard, T-Pro |
| `usage_band` | L12M transaction slab before upgrade (a.Zero → k.Grt 1000) |
| `prior_status` | Pre-upgrade activity (Inactive / Non Starter / Others) |
| `channel` | Acquisition channel (Sales / DIY / Service / Others) |
| `upgrade_type` | New plan (`na`) or plan swap (`replacement`) |
| `onboard_status` | Active/Inactive at month of upgrade (M0) |
| `engagement_tag` | Whether customer was actively worked by team |
| `base` | Customer count in this cohort-segment |
| `m0_active` → `m6_active` | Customers active each month post-upgrade |
| `m0_txn` → `m6_txn` | Transaction volume per month |
| `m0_gmv` → `m6_gmv` | Revenue (₹) per month |

Suffix variants: `_bc` = billing-cycle active · `_3plus` = 3+ active days · `_addtn` = delta vs M-1

---

## Notes on Sample Data

Values are scaled and plan tier names are generic — safe to share publicly. The structural patterns (cohort shapes, metric relationships, filter cardinality) reflect a real SaaS post-upgrade pipeline.

---

## How to Publish (GitHub Pages)

1. Create a new GitHub repo: `subscription-cohort-dashboard`  
2. Upload all 3 files  
3. Go to **Settings → Pages → Deploy from branch → main → / (root)**  
4. Your site will be live at `https://YOUR-USERNAME.github.io/subscription-cohort-dashboard/`
