# Retail Sales Analytics | From Excel to Power BI

### From my first 12-row Excel dashboard to a four-page Business Intelligence report

![Excel](https://img.shields.io/badge/Excel-PivotTables%20%26%20Dashboards-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-DAX%20%26%20Data%20Modeling-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power_Query-Data%20Cleaning-0F766E?style=flat-square)
![Dataset](https://img.shields.io/badge/Data-500%20Synthetic%20Transactions-2563EB?style=flat-square)

> **The idea:** I wanted to learn how to go beyond creating charts and start using sales data to answer questions a business might actually ask.

**Tools:** Microsoft Excel · PivotTables · PivotCharts · Power Query · Power BI · DAX · Data Modeling  
**Data:** Two synthetic retail datasets (12 transactions, then 500 transactions)  
**Main reporting period:** January–September 2026


**Explore the documentation:** [Business questions & recommendations](docs/BUSINESS_QUESTIONS.md) · [DAX measures & data model](docs/DAX_MEASURES.md) · [How to open the dashboards](docs/HOW_TO_EXPLORE.md)

---

##  About this project

This project started when I decided to improve my practical data analytics skills. Although I'd studied Data Science, I wanted to get more comfortable with tools that businesses use to understand performance and make decisions.

I didn't start with a complex dashboard. I began with **just 12 retail transactions in Excel**. I learned how to calculate revenue, summarize sales with PivotTables, build charts, and create my first interactive dashboard.

Once I understood those basics, I challenged myself with **500 transactions** across nine months, four regions, two sales channels, and ten products. That gave me more interesting questions to explore.

Finally, I moved the same 500-transaction analysis into **Power BI**. I used Power Query to prepare and validate the data, built a Date table, wrote DAX measures, and created an interactive four-page report with product drill-through.

So this repository tells **one connected story**: how I went from learning the basics in Excel to building a more complete Business Intelligence reporting solution.

> **A note about the data:** Both datasets are synthetic and were used for learning. The analysis describes a simulated business; it is not a claim about a real retailer or real customer behavior.

## The journey

| Stage | What I worked on | Why it mattered |
| --- | --- | --- |
| **1. Excel foundations** | 12 transactions, revenue calculations, PivotTables, first dashboard | Understand the basic numbers before worrying about design |
| **2. Excel at a larger scale** | 500 transactions, KPIs, monthly/region/channel analysis, slicers | Compare performance across different parts of a business |
| **3. Power Query** | Data types, missing values, clean text, revenue validation | Check whether the numbers behind the dashboard are reliable |
| **4. Power BI + DAX** | Date model, reusable measures, monthly growth, rankings | Ask questions that simple totals can't answer |
| **5. Business storytelling** | Four report pages, product drill-through, written findings | Help someone move from an overview to the detail behind it |

##  Part 1 — Where I started: my first Excel dashboard

My first workbook contained **12 orders** for products including laptops, monitors, keyboards, mice, and headphones.

At that point I was learning what Excel could do beyond storing rows and columns. I organized the transaction data, calculated revenue, built PivotTables, and used PivotCharts and filtered KPIs to make the results easier to explore.

| First Excel dataset | Result |
| --- | ---: |
| Transactions | **12** |
| Total revenue (all categories) | **£5,315.00** |
| Average revenue per order | **£442.92** |
| Laptop revenue | **£3,000.00** |
| Electronics revenue | **£3,900.00** |

One small but useful lesson came from the dashboard filters. The workbook was saved with **Electronics selected**, so the visible KPI showed **£3,900 and five transactions**, not the full £5,315. It helped me understand that a dashboard number only makes sense when you know **what has been filtered**.

The first project was simple, but it gave me enough confidence to try a larger dataset.

##  Part 2 — Taking Excel further with 500 transactions

The next dataset contained **500 unique orders from January to September 2026**, with fields for dates, products, categories, quantities, unit prices, revenue, regions, and sales channels.

I built PivotTables for **monthly performance, regional performance, sales channels, and KPIs**, then brought them into a second interactive Excel dashboard.

This time I wanted to think more like someone preparing a report for a manager: *Are we selling more? Where does revenue come from? Does the busiest channel bring in the most money?*

### Overall sales performance

| KPI | Full-dataset result |
| --- | ---: |
| **Total revenue** | **£160,935.05** |
| **Unique orders** | **500** |
| **Average order value** | **£321.87** |
| Total units sold | 1,036 |
| Average units per order | 2.07 |
| Period | Jan–Sep 2026 |

**Important filter detail:** The 500-order Excel dashboard was saved with **In-store** selected. Its displayed **£77,860.35 and 263 orders** are correct for that filter, but are *not* the full-dataset totals above. I clear or label filters when presenting the overall business performance.

## Part 3 — Why I moved to Power BI

By this point, I had already built a working Excel dashboard. I didn't want to repeat exactly the same work in another tool; I wanted to take the analysis further.

I imported the 500 transactions into **Power BI Desktop** and used **Power Query** to check column types, review missing values, clean text, and create a calculated revenue check using **Units × Unit Price**.

The checks confirmed **500 distinct Order IDs, no blank fields, and no revenue mismatches** in the uploaded dataset.

Next, I created a **Date table** and linked it to the sales data. That made it possible to calculate revenue changes between months and keep time-based analysis consistent across visuals.

### DAX measures I built

| Measure | What it helps answer |
| --- | --- |
| **Total Revenue** | How much did we sell? |
| **Total Orders** | How many unique orders were placed? |
| **Average Order Value** | How much is an order worth on average? |
| **Previous Month Revenue** | What did the previous month generate? |
| **Revenue MoM Change / Growth %** | Is revenue increasing or decreasing month to month? |
| **Revenue Contribution %** | How much does each channel contribute? |
| **Average Units Per Order** | Are people buying more items per transaction? |
| **Product Revenue Rank** | Which products are top revenue contributors within the selected filters? |

### The four Power BI report pages

| Report page | What someone can explore |
| --- | --- |
| **Executive Overview** | Main KPIs, revenue trend, channel performance, filters |
| **Product Analysis** | Categories, Top 5 products, product ranks, performance table |
| **Sales Drivers** | Monthly growth, regional revenue, channel contribution, units per order |
| **Product Details** | Product-level drill-through, KPIs, monthly trend, region comparison |

The drill-through feature was especially useful to learn. Rather than stopping at a product bar on a chart, I could open a dedicated page and investigate that product in more detail.

---

##  Business questions I wanted to answer

Building the visuals was one part of the project. The more interesting part was trying to work out what the numbers were telling me — and what they *weren't* telling me.

### 1. Which channel makes more revenue?

| Channel | Revenue | Orders | Average order value | Revenue share |
| --- | ---: | ---: | ---: | ---: |
| **Online** | **£83,074.70** | 237 | **£350.53** | **51.62%** |
| **In-store** | £77,860.35 | **263** | £296.05 | 48.38% |

**What I noticed:** Online generated more revenue, even though In-store had more transactions. I learned why it's worth looking at **both order volume and order value**, rather than choosing one KPI and calling it a day.

### 2. Are Online orders worth more because people buy more items?

Surprisingly, **not in this dataset**.

- **Online:** about **2.03 units per order**
- **In-store:** about **2.11 units per order**

Despite slightly fewer units per transaction, Online had the higher average order value. That made me curious about **which products were being purchased and their prices**, rather than assuming customers bought more items online.

The data shows the difference; it doesn't by itself establish its cause.

### 3. Which months were strongest and weakest?

| Month | Revenue | Month-over-month change |
| --- | ---: | ---: |
| Jan | £16,581.60 | — |
| Feb | £20,026.65 | +20.78% |
| Mar | £18,787.85 | −6.19% |
| **Apr** | **£14,219.05** | **−24.32%** |
| **May** | **£20,319.90** | **+42.91%** |
| Jun | £16,346.75 | −19.55% |
| Jul | £17,238.05 | +5.45% |
| Aug | £17,890.00 | +3.78% |
| Sep | £19,525.20 | +9.14% |

**What stood out:** April was the weakest month, followed by the strongest month, May, with a **42.91% rebound**. In a real retail business, that would be something I'd investigate using promotion, stock, demand, and historical data. I wouldn't call it seasonality or credit a campaign without evidence.

### 4. Which region brought in the most revenue?

| Region | Revenue | Orders |
| --- | ---: | ---: |
| **Leeds** | **£44,122.00** | 128 |
| Birmingham | £42,421.85 | 127 |
| Manchester | £40,467.55 | 128 |
| London | £33,923.65 | 117 |

**What I noticed:** Leeds led in revenue for the complete dataset. But that doesn't automatically make it the most profitable region. I'd need information such as store numbers, operating costs, and footfall to make that judgment.

### 5. Which category contributed most?

| Category | Revenue | Orders |
| --- | ---: | ---: |
| **Electronics** | **£123,611.25** | 202 |
| Accessories | £37,323.80 | **298** |

**What I noticed:** Electronics generated most revenue even though Accessories appeared in more orders. Another reminder that **frequency isn't the same thing as value**.

### 6. What were the highest-revenue products?

| Rank | Product | Revenue |
| --- | --- | ---: |
| 1 | **Laptop** | **£58,045.00** |
| 2 | Tablet | £27,568.00 |
| 3 | Monitor | £27,562.50 |
| 4 | Docking Station | £11,436.75 |
| 5 | Speaker | £10,435.75 |

Laptops alone contributed about **36.07%** of total revenue. That raises a useful business question: *How reliant is the retailer on a single product?* Without cost, margin, and inventory information, I can't tell whether that concentration is good or risky.

### 7. Is the most frequently ordered product also the biggest revenue generator?

**No.** Monitor appeared in **59 orders**, compared with **39 orders for Laptop**, but Laptop earned considerably more revenue.

I learned that rankings change depending on whether we measure **orders, units, revenue, or profit**. The last one can't be calculated from this dataset.

### 8. What would I recommend to a business manager?

If this were real operational data, I'd suggest a few **follow-up investigations**:

- **Basket value:** Explore Online and In-store product mix and unit prices before considering ways to improve In-store order value.
- **Monthly changes:** Find out what happened around the April dip and May rebound, using a longer history and business context.
- **Product concentration:** Check laptop margins, demand, and availability instead of relying on revenue alone.
- **Regional performance:** Investigate the difference between Leeds and London using footfall, costs, promotions, and store coverage.

These are **questions and hypotheses**, not proven commercial interventions. I think making that distinction is part of doing responsible analysis.

---

##  What I learned

Looking back, the biggest difference between my first Excel dashboard and the Power BI report isn't just that the report has more charts.

It's **how I approach the data**.

At first I was focused on learning the mechanics: calculating revenue, making PivotTables, adding slicers. Later, I started asking more questions about the meaning behind the numbers.

Why can a channel with fewer orders generate more revenue? Does a product that appears in lots of orders necessarily contribute more sales? What could explain a sudden monthly change?

I also learned to think about data quality before presentation, use DAX measures rather than repeating manual calculations, and design reports that let someone explore details for themselves.

Most importantly, **finding a pattern and explaining why it happened are two different things**. A dashboard is a good starting point for decision-making, but sometimes the most useful outcome is identifying what additional data is needed.

## Limitations

This is a **learning project using synthetic transactions**, not actual business data.

The 500-order dataset covers only nine months and doesn't include customer identifiers, profit margins, returns, marketing activity, stock, store costs, or footfall. So I can't reliably calculate retention, profitability, or explain *why* a particular month, product, or region performed as it did.

I have tried to be clear about what the available data supports and where further investigation would be needed.

##  Project files and how to explore them

This repository is intended to bring the complete learning journey together:

\`\`\`text
retail-sales-excel-powerbi-analytics/
├── README.md
├── excel/
│   ├── Retail_Sales_Analysis_.xlsx
│   └── Retail_Sales_Analytics_500_Transactions.xlsx
├── powerbi/
│   └── Retail_Sales_Analytics_500.pbix
└── screenshots/
    ├── excel-foundations.png
    ├── excel-500-dashboard.png
    ├── executive-overview.png
    ├── product-analysis.png
    ├── sales-drivers.png
    └── product-details.png
\`\`\`

**Publication note:** The structure above is the *planned complete repository*. The original Excel workbooks, Power BI file, and screenshots still need to be uploaded; the README is being published first.

When the files are available:

1. Open each workbook in **Microsoft Excel** to explore the source data, PivotTables, dashboards, and slicers.
2. Open the \`.pbix\` file in **Power BI Desktop**.
3. If Power BI can't find the source workbook, update the Excel file path in Power Query, then refresh.
4. Clear any saved slicer selections to compare the **unfiltered** totals with the figures above.
5. Use the **Product Details** drill-through page to explore selected products.

## Final thoughts

I started this project with **12 orders and a basic spreadsheet**. I ended up working with **500 transactions**, a more detailed Excel dashboard, and a **four-page Power BI report**.

There's still more I want to learn, but this project gave me practical experience taking data from preparation through to analysis and presentation. For me, that was the main goal: **not just learning tools, but learning how to use them to ask better business questions**.

---

**Author:** Kiruthik Raam D V  
**Focus:** Data Analytics · Business Intelligence · Power BI · Excel  
**LinkedIn:** [Connect with me](https://www.linkedin.com/in/kiruthik-raam-d-v-41123640b) · **GitHub:** [KiruthikRaamDV](https://github.com/KiruthikRaamDV)
