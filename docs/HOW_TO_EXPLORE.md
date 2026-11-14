# Opening the Excel and Power BI project

## What the files represent

- `excel/Retail_Sales_Analysis_.xlsx` — the **first Excel exercise**, based on 12 transactions and a basic dashboard.
- `excel/Retail_Sales_Analytics_500_Transactions.xlsx` — the expanded **500-transaction Excel project**, including PivotTables, analysis sheets and an interactive dashboard.
- `powerbi/Retail_Sales_Analytics_500.pbix` — Power BI Desktop report based on the 500-transaction workbook.
- `screenshots/` — static images of the dashboards and report pages.

> These binary project files are added separately from the README and documentation. If the links are missing, they have **not yet been uploaded to GitHub**.

## Excel walkthrough

1. Open the 12-order workbook in Microsoft Excel.
2. Start at `RetailSales` to see the underlying data, then explore the PivotTables and `Dashboard`.
3. Open the 500-order workbook.
4. Start with `Sales Data`, then look at `Monthly Analysis`, `Regional Analysis`, `Channel Analysis`, and `Dashboard`.
5. Clear the channel/category selections if you want to compare against **overall** totals.

**Saved state:** The 12-order dashboard shows an Electronics filter; the 500-order dashboard shows an In-store filter. Filtered numbers will be lower than overall revenue.

## Power BI walkthrough

1. Install and open **Power BI Desktop**.
2. Open the `.pbix` file.
3. If the query shows an error because the original workbook path belongs to another computer, open **Transform data → Data source settings** and update it to the downloaded 500-transaction workbook.
4. Select **Close & Apply**, then **Refresh**.
5. Explore **Executive Overview**, **Product Analysis**, **Sales Drivers**, and **Product Details**.
6. Use Region, Channel and Category slicers to see the KPIs change.
7. Right-click a product on a relevant product chart and choose **Drill through → Product Details**.

## Expected totals, with all filters cleared

| Measure | Expected |
| --- | ---: |
| Revenue | £160,935.05 |
| Unique orders | 500 |
| Average order value | £321.87 |
| Online revenue | £83,074.70 |
| In-store revenue | £77,860.35 |

If your numbers differ, check that you are using the same 500-order dataset and that no slicers or report-level filters are still applied.

## Reproducibility note

The project uses a practice dataset, not a live database. It does not need online services or API keys to reproduce the Excel and Power BI reporting. The published `.pbix` may still require updating the local Excel source path.
