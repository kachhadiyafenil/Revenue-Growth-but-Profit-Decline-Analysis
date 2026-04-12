# 📊 Revenue Growth but Profit Decline — Root Cause Analysis

> A Power BI dashboard project investigating why revenue is growing but profit margins are eroding across product categories.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-blue?style=flat)
![Dataset](https://img.shields.io/badge/Dataset-Sample%20Superstore-orange?style=flat)

---

## 📌 Problem Statement

The company is experiencing steady revenue growth, but profit is not keeping pace — and the gap is widening. This project identifies the root causes impacting profitability, with a focus on discounting behavior, loss-making products, and return rates.

---

## 🎯 Objectives

- Analyze revenue vs. profit trends over time
- Identify loss-making categories and sub-categories
- Investigate the impact of discounts and product returns
- Provide actionable business recommendations

---

## 📁 Dataset

**Source:** [Sample Superstore Dataset — Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

| Table | Description |
|-------|-------------|
| `Orders` | Transaction-level sales, profit, discount, and product data |
| `Returns` | Order return records linked to the Orders table |
| `People` | Regional manager assignments |

---

## 🧠 Key KPIs (DAX Measures)

| KPI | DAX Logic |
|-----|-----------|
| Total Revenue | `SUM(Orders[Sales])` |
| Total Profit | `SUM(Orders[Profit])` |
| Profit Margin % | `DIVIDE([Total Profit], [Total Revenue])` |
| Profit per Order | `DIVIDE([Total Profit], DISTINCTCOUNT(Orders[Order ID]))` |
| Return Rate % | `DIVIDE([Returned Orders], [Total Orders])` |
| Avg Discount % | `AVERAGE(Orders[Discount])` |

---

## 📊 Dashboard Structure

### 🟢 Page 1 — Overview
- Revenue vs. Profit trend (line chart)
- KPI summary cards: Revenue, Profit, Margin %, Profit per Order

**Insight:** Revenue grows steadily year-over-year, but profit fluctuates and consistently lags — the gap between them widens over time.

---

### 🟡 Page 2 — Problem Area Analysis
- Profit by Category (bar chart)
- Profit by Sub-Category (sorted bar chart)

**Insight:** Furniture is the least profitable category. Tables and Bookcases generate **negative profit**, dragging down overall margins.

---

### 🔴 Page 3 — Root Cause Analysis
- Avg Discount % by Sub-Category
- Return Rate % by Sub-Category

**Insight:**

| Sub-Category | Avg Discount | Return Rate |
|---|---|---|
| Tables | ~26% | ~9.7% |
| Bookcases | ~21% | ~6.7% |

Excessive discounting is the primary driver of negative margins. High return rates compound the losses further.

---

## 💡 Business Recommendations

1. **Redesign discount strategy** — Set category-level discount caps. Tables and Bookcases are being discounted past the break-even point.
2. **Reprice or discontinue loss-making SKUs** — Review base pricing for sub-categories with consistently negative margins before discounting applies.
3. **Investigate high return rates** — Determine whether product quality, delivery issues, or misaligned customer expectations are driving returns in Furniture.
4. **Redirect focus to high-margin categories** — Allocate marketing and inventory investment toward categories with healthy, growing margins (e.g., Technology, Office Supplies).

---

## 📸 Dashboard Preview

<img width="1175" height="662" alt="Screenshot 2026-04-12 084755" src="https://github.com/user-attachments/assets/a829f516-d5bb-4997-a41f-4af43ef557ac" />



> **Tip:** Export screenshots from Power BI via **File → Export → Export to PNG** or use the Snipping Tool on each report page.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard development and data visualization |
| DAX | Custom KPI measures and calculated columns |
| Power Query (M) | Data transformation and relationship modeling |
| Sample Superstore | Source dataset (Orders, Returns, People tables) |

---

## 🚀 Key Learnings

- Building a data model with multiple related tables (star schema)
- Writing DAX measures for business KPIs (margin, return rate, profit per order)
- Designing dashboards with a narrative structure: Overview → Problem → Cause
- Performing root cause analysis by layering discount and return data

---

## 🏁 How to Run

1. Download the `.pbix` file from the `/pbix` folder
2. Open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. If prompted, relink the data source to the `.csv` file in `/dataset`
4. Explore all three report pages in the bottom tab bar

---

## 👤 Author

**Fenil Kachhadiya**  
Business Intelligence | Power BI | Data Analytics

---

*Dataset credit: [Tableau Sample Superstore](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final) via Kaggle*
