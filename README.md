# Retail Sales Analytics — From Excel to Power BI

**A personal project about learning to work with data, build useful reports, and ask better business questions.**

**Project status:** Completed  
**Tools:** Excel, PivotTables, PivotCharts, Power Query, Power BI, DAX  
**Main dataset:** 500 synthetic retail transactions, January–September 2026

[Explore the Excel workbook](excel/Retail_Sales_Analytics_500_Transactions.xlsx) · [Open the Power BI report](powerbi/Retail%20Sales%20Analytics%20500.pbix) · [Browse screenshots](screenshots/) · [Read the business analysis](docs/BUSINESS_QUESTIONS.md)

---

## How it started

I wanted to get more comfortable using the tools that businesses rely on to understand their data. Rather than jump straight into a large Power BI report, I started with a small Excel exercise.

My first dataset had just **12 sales transactions**. I practiced calculating revenue, creating PivotTables and charts, and bringing the results into a simple interactive dashboard. It wasn't complicated, but it helped me understand how to organize data and how filters change what a dashboard shows.

Once I was comfortable with that, I worked on a larger dataset with **500 orders** across nine months, four regions, two sales channels, and ten products. This time, I wanted to answer questions a manager might actually ask: Which channel brings in more revenue? Which products matter most? How do sales change from month to month?

Excel was a good place to explore those questions. Power BI was the next step because I wanted reusable calculations, a proper data model, and the ability to drill into the detail behind a chart.

The result is one connected project: **Excel foundations → larger Excel dashboard → Power Query and DAX → a four-page Power BI report**.

## A look at the dashboards

| Excel sales dashboard | Power BI report |
| --- | --- |
| ![Excel dashboard screenshot](screenshots/Screenshot%202026-11-13%20102423.png) | ![Power BI report screenshot](screenshots/Screenshot%202026-11-14%20155100.png) |

[View all project screenshots](screenshots/)

*Screenshots may show selected filters. The figures below refer to the complete 500-transaction dataset unless stated otherwise.*

## The business in numbers

| Metric | Result |
| --- | ---: |
| Total revenue | **£160,935.05** |
| Unique orders | **500** |
| Average order value | **£321.87** |
| Units sold | 1,036 |
| Reporting period | Jan–Sep 2026 |

The dataset is **synthetic**, created for analysis practice. These are not real retailer results.

## What I built

### 1. Excel — getting comfortable with the data

I started with the 12-order exercise, then developed a more detailed workbook using the 500 transactions.

In Excel, I worked with revenue calculations, PivotTables, PivotCharts, and interactive slicers. I built summaries for monthly revenue, regional sales, Online versus In-store performance, and key metrics such as order count and average order value.

That gave me an initial dashboard and a better idea of which questions I wanted to explore further.

### 2. Power Query — checking the data before reporting

I brought the 500-transaction workbook into Power BI and used Power Query to review data types, clean text fields, check for missing values, and validate revenue against **Units × Unit Price**.

The checks found **500 distinct Order IDs**, no missing values, and no revenue mismatches.

This stage reminded me that a polished dashboard only helps if the numbers behind it can be trusted.

### 3. Power BI and DAX — taking the analysis further

I created a Date table, linked it to the sales data, and wrote DAX measures for total revenue, total orders, average order value, previous-month revenue, month-over-month growth, channel revenue contribution, average units per order, and product rankings.

I also learned how to make the report interactive with slicers and a drill-through page.

The Power BI report has four pages:

| Page | What it shows |
| --- | --- |
| **Executive Overview** | Main KPIs, revenue trends, channel performance and filters |
| **Product Analysis** | Category comparisons, top products and dynamic rankings |
| **Sales Drivers** | Monthly growth, regional results and basket-size comparisons |
| **Product Details** | Product-specific performance using drill-through |

[See the DAX measures and model notes](docs/DAX_MEASURES.md)

## The questions that made the project interesting

### Does the channel with more orders make more revenue?

Not in this dataset.

| Channel | Orders | Revenue | Average order value |
| --- | ---: | ---: | ---: |
| Online | 237 | **£83,074.70** | **£350.53** |
| In-store | **263** | £77,860.35 | £296.05 |

In-store had more transactions, but Online generated more revenue. That helped me see why order count alone is not enough to judge performance.

### Are Online orders bigger because customers buy more items?

Actually, In-store orders contained slightly more units on average: **2.11 versus 2.03 Online**.

So I wouldn't assume quantity explains the higher Online order value. I'd want to investigate product mix and item prices before recommending changes to either channel.

### When did sales change the most?

**April** was the weakest month at **£14,219.05**. **May** was the strongest at **£20,319.90**, a **42.91% increase** from April.

The monthly growth calculation made that jump easy to spot. But it didn't explain *why* it happened. In a real business, I'd want to look at promotions, stock availability and a longer history.

### Which region and product contributed most?

**Leeds** had the highest revenue of the four regions, at **£44,122**.

**Laptop** was the top-revenue product at **£58,045**, or about **36% of total revenue**.

These findings are useful starting points. They also raise further questions about store coverage, profit margins, inventory and reliance on particular products — none of which can be answered using revenue alone.

[Read all business questions, findings and follow-up recommendations](docs/BUSINESS_QUESTIONS.md)

## What I learned

Looking back, the biggest change wasn't simply moving from Excel to Power BI. It was the way I started thinking about the analysis.

At first, I was concentrating on how to build PivotTables and charts. Later, I became more interested in what each number meant, how filters affected the answer, and what additional information a business would need before acting on a finding.

I also learned to separate **what the data shows** from **what might explain it**. A dashboard can reveal a pattern, but it doesn't automatically prove the reason behind it.

That's the part of this project I'm most pleased with: it gave me practical experience across the full process, from preparing data to communicating a result clearly.

## Project files

The completed 500-transaction Excel and Power BI work, along with screenshots, is available in this repository.

| Location | What's included |
| --- | --- |
| [Excel workbook](excel/Retail_Sales_Analytics_500_Transactions.xlsx) | Raw sales data, analysis sheets, PivotTables, charts and the interactive dashboard |
| [Power BI report](powerbi/Retail%20Sales%20Analytics%20500.pbix) | Four-page report with Power Query transformations, DAX measures and drill-through |
| [Screenshots](screenshots/) | Captures from the Excel and Power BI work |
| [DAX and modeling notes](docs/DAX_MEASURES.md) | Core measures and the Date-table relationship |
| [Business questions](docs/BUSINESS_QUESTIONS.md) | Findings, interpretations and recommendations |
| [How to explore the files](docs/HOW_TO_EXPLORE.md) | Instructions for opening and refreshing the reports |

**About the first Excel exercise:** The 12-transaction workbook was part of the learning journey, but its original file is not currently included in this repository. The downloadable Excel workbook above is the later, 500-transaction version.

### To explore the report yourself

Download the Excel workbook and open it in Microsoft Excel. Download the `.pbix` file and open it using Power BI Desktop.

If Power BI asks for the original Excel source path, update it to the downloaded workbook and refresh. Clear any saved slicer selections to compare your results with the overall figures in this README.

[Full setup notes](docs/HOW_TO_EXPLORE.md)

## Limitations

This is a learning project with synthetic data, not a report about a real retailer. The dataset covers only nine months and doesn't include costs, profit margins, customer identifiers, marketing activity or inventory records.

For that reason, I can describe sales patterns, but I can't make reliable claims about profitability, customer retention or what caused the changes.

---

**Kiruthik Raam D V** · [GitHub](https://github.com/KiruthikRaamDV) · [LinkedIn](https://www.linkedin.com/in/kiruthik-raam-d-v-41123640b)
