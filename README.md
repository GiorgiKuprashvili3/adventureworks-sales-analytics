# 📊 AdventureWorks Sales Analytics

> A full analytical deep-dive into 4 years of AdventureWorks sales data using **SQL Server** and **Excel**.  
> Built to answer real business questions about seasonality, profitability, discounts, and product performance.

---

## 🗂️ Project Structure

```
adventureworks-sales-analytics/
│
├── sql/
│   └── adventureworks_analysis.sql   # Full SQL code with inline documentation
│
├── docs/
│   ├── Presentation_Final.pdf         # Management-ready presentation
│   └── External_Documentation.pdf    # Full written documentation
│
└── README.md
```

---

## ❓ Business Questions

| # | Question | Status |
|---|----------|--------|
| 1 | Is sales revenue seasonal? | ✅ Answered |
| 2 | Are sales and profits growing year-over-year? | ✅ Answered |
| 3 | Why does margin fluctuate? | ✅ Answered |
| 4 | Which categories and products drive real profit? | ✅ Answered |
| 5 | How do discounts affect profitability? | ✅ Answered |

---

## 🔑 Key Findings

### 💰 Profitability
- **Bikes** generate ~80% of total company profit
- **Accessories** have 50–60% margin — underutilized growth opportunity
- **Clothing** (Jerseys, Caps) is persistently loss-making

### 📅 Seasonality
- **Q1 & Q4** are the strongest profit quarters
- **Q2 (April–June)** is structurally weak every year
- Revenue is stable year-round — margin swings are driven by **product mix**, not demand

### 🏷️ Discounts
| Discount Level | Avg Margin | Total Profit |
|----------------|------------|--------------|
| 0% | 30% | +$11,264,979 |
| 0–10% | 7% | -$260,949 |
| 10–30% | -74% | -$922,772 |
| 30%+ | -306% | -$709,354 |

> ⚠️ Any discount above 5% severely damages profitability

### 🚨 Critical Issue Found
- **~29,000 transactions** show negative profit with **0% discount**
- Products were sold below `StandardCost` without any discount recorded
- This is a **pricing system failure**, not a discounting problem

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| SQL Server (T-SQL) | Data extraction, transformation, analysis |
| Excel | Charts, pivot tables, dashboard |
| AdventureWorks 2022 | Source database |

---

## 📐 Methodology

```
Phase 0 → Data Exploration
Phase 1 → Create General_Panel (SQL View)
Phase 2 → Data Quality & Integrity Checks
Phase 3 → Seasonality Analysis (Monthly & Quarterly)
Phase 4 → Yearly Trend Analysis
Phase 5 → Discount & Margin Analysis
Phase 6 → Category & Product Profitability
Phase 7 → Conclusions & Recommendations
```

---

## ✅ What's Done / 🔜 What's Next

### ✅ Done
- [x] SQL analytical panel (`General_Panel` view)
- [x] Data quality checks
- [x] Seasonality & trend analysis
- [x] Discount impact analysis
- [x] Category & subcategory profitability
- [x] Product-level loss maker diagnostics
- [x] Management presentation
- [x] Full external documentation

### 🔜 Planned
- [ ] Power BI / Tableau interactive dashboard
- [ ] Python version of the analysis (pandas)
- [ ] Automated monthly monitoring report
- [ ] Price floor alert system simulation

---

## 📁 How to Run

1. Restore **AdventureWorks2022** to SQL Server  
   → [Download here](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)
2. Open `sql/adventureworks_analysis.sql`
3. Run **top to bottom** — phases are clearly marked with comments
4. The script creates `dbo.General_Panel` and all analysis queries

---

## 📌 Top 5 Most Profitable Products
1. Mountain-200 Black, 42
2. Mountain-200 Black, 38
3. Mountain-200 Black, 46
4. Mountain-200 Silver, 38
5. Road-150 Red, 48

## 🔴 Top 5 Biggest Loss-Making Products
1. Road-650 Red, 44
2. Touring-1000 Yellow, 60
3. Road-650 Red, 60
4. Touring-1000 Yellow, 46
5. Road-650 Black, 52

---

## 💡 Recommendations

**High Priority**
- Enforce discount caps — no discount above 5% without manager approval
- Implement price floor: `UnitPrice` must never fall below `StandardCost`
- Fix pricing for Road-650, Touring Frames, Jerseys, Caps

**Medium Priority**
- Promote Accessories (Helmets, Racks, Tires) — high margin, low risk
- Remove or reprice persistently unprofitable SKUs
- Build category mix dashboard for monthly monitoring

**Low Priority**
- Optimize seasonal purchasing based on product mix trends
- Rebuild long-term pricing strategy (good/better/best structure)

---

*Dataset: AdventureWorks 2022 | Period: 2011–2014 | ~121,000 transactions*
