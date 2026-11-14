# How to explore the project

This is an Excel-to-Power-BI learning project built with synthetic retail data.

## Download the files

- [500-transaction Excel workbook](../excel/Retail_Sales_Analytics_500_Transactions.xlsx)
- [Completed Power BI report](../powerbi/Retail%20Sales%20Analytics%20500.pbix)
- [Dashboard screenshots](../screenshots/)

The story began with a separate 12-transaction Excel exercise. The original small workbook is not yet in this repository; the complete 500-transaction workbook and Power BI report are available above.

## Excel walkthrough

1. Open the 500-transaction workbook in Microsoft Excel.
2. Start with `Sales Data` and inspect the raw fields.
3. Explore the monthly, regional and channel analysis worksheets, the KPI PivotTables and the dashboard.
4. Test the Channel slicer. The saved dashboard shows the **In-store** filter, so it displays £77,860.35 and 263 orders.
5. Clear the slicer to compare the **overall** revenue and order count with the figures below.

## Power BI walkthrough

1. Open the `.pbix` file in Power BI Desktop.
2. If the source workbook path no longer exists on your computer, open **Transform data → Data source settings** and point the query to the downloaded Excel workbook.
3. Select **Close & Apply** and refresh the data.
4. Explore **Executive Overview**, **Product Analysis**, **Sales Drivers** and **Product Details**.
5. Try the Region, Channel and Category slicers and see how the measures respond.
6. Right-click a product bar and use **Drill through → Product Details** where available.

## Expected totals without filters

| Measure | Result |
| --- | ---: |
| Total revenue | £160,935.05 |
| Unique orders | 500 |
| Average order value | £321.87 |
| Online revenue | £83,074.70 |
| In-store revenue | £77,860.35 |

If you see different numbers, first check for slicer selections and report-level filters.

## A note about reproducibility

The datasets are synthetic, and the report does not require a live data service or API key. Depending on where you save the files, Power BI may need the local workbook path updated before you can refresh it.

[Back to the project case study](../README.md)
