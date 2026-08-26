# Superstore Executive Sales Dashboard

An interactive Power BI dashboard analyzing 4 years (2015–2018) of Superstore retail sales data, built to support management-level decision-making — regional performance, category trends, customer retention, and year-over-year growth.

![Dashboard Screenshot](screenshots/full-dashboard.png)

---

## Overview

**Dataset:** Superstore Sales (9,800 rows · 4,922 orders · 793 customers)
**Tool:** Power BI Desktop
**Focus:** A single-page executive view prioritizing clear decision-support metrics over decorative visuals.

---

## Key Metrics (KPI Cards)

| Metric | Value |
|---|---|
| Total Sales | $2.26M |
| Total Orders | 4,922 |
| Total Customers | 793 |
| Average Sales per Order | $459 |
| Repeat Customer Rate | 98.36% |
| YoY Sales Growth (2018 vs 2017) | +20.30% |

---

## Key Findings

- **2016 was a decline year** (-4.26% YoY), followed by strong recoveries in **2017 (+30.64%)** and **2018 (+20.30%)** — 2018 stands as the strongest year overall on total revenue.
- **Technology** is the strongest-performing category by total sales.
- **West** leads all regions in sales; **South** trails behind every other region.
- **South has a notably high average order value despite low total sales** — its shortfall comes from fewer customers and fewer orders per customer, not smaller basket sizes. This points to a customer-acquisition gap rather than a pricing or product problem.
- **Phones and Chairs** are the top two sub-categories by revenue.
- The **top 10 individual products contribute only ~11%** of total sales — revenue is broadly distributed across the catalog rather than concentrated in a handful of SKUs.
- **98.36% of customers are repeat buyers** — with ~6.2 orders per customer on average, retention is a defining feature of this customer base.

---

## Dashboard Structure

- **KPI strip** — 6 headline cards (Total Sales, Orders, Customers, AOV, YoY Growth, Repeat Rate)
- **Monthly Sales Trend** — a 48-month line chart (2015–2018) showing the dip-and-recovery pattern
- **Regional Sales** — bar chart flagging the South region's low-reach pattern
- **Category Sales** — bar chart, Technology highlighted as the leading category
- **Sub-Category Sales** — Top 5 by revenue
- **Customer & Segment Mix** — donut (Consumer / Corporate / Home Office) plus a repeat-vs-one-time customer split
- **Slicers** — Year, Region, Segment, for interactive drill-down

---

## Data Model

- Single `Sales` fact table plus a dedicated `DateTable` (marked as the model's date table) related on `Order Date`.
- Key DAX measures: `Total Sales`, `Total Orders`, `Total Customers`, `Avg Sales per Order`, `YoY Sales Growth %` (via `SAMEPERIODLASTYEAR`), `Repeat Customer Rate` (customers with more than one distinct order, evaluated across their full purchase history).

---

## Files

- `dashboard.pbix` — the full Power BI file (open in Power BI Desktop to explore interactively)
- `/screenshots` — static views of the dashboard and individual visuals

---

## Notes

Built as a hands-on project to practice the full Power BI workflow: data modeling, DAX measure design, and executive-level dashboard layout — including debugging real issues along the way (aggregation defaults on the KPI visual, date-axis granularity, text-type calculated columns) rather than a from-a-template build.
