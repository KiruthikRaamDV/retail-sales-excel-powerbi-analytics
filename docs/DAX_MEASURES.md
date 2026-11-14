# Power BI model and DAX measures

This document records the core calculations explored in the 500-transaction Power BI report. It is intended as a learning reference alongside the \`.pbix\` project.

## Model

- **Fact table:** \`Sales Data\` — each row is one transaction, identified by \`Order ID\`.
- **Date table:** \`Date Table\` — one row per calendar date.
- **Relationship:** \`Date Table[Date]\` (one) → \`Sales Data[Order Date]\` (many), active and single-direction.
- **Time axis:** \`Date Table[Year-Month]\`, sorted chronologically.

## Core measures

\`\`\`dax
Total Revenue =
SUM('Sales Data'[Revenue (£)])

Total Orders =
DISTINCTCOUNT('Sales Data'[Order ID])

Average Order Value =
DIVIDE([Total Revenue], [Total Orders], 0)

Average Units Per Order =
DIVIDE(SUM('Sales Data'[Units]), [Total Orders], 0)
\`\`\`

## Month-over-month calculations

\`\`\`dax
Previous Month Revenue =
CALCULATE(
    [Total Revenue],
    DATEADD('Date Table'[Date], -1, MONTH)
)

Revenue MoM Change =
IF(
    ISBLANK([Previous Month Revenue]),
    BLANK(),
    [Total Revenue] - [Previous Month Revenue]
)

Revenue MoM Growth % =
VAR PreviousRevenue = [Previous Month Revenue]
RETURN
    IF(
        ISBLANK(PreviousRevenue),
        BLANK(),
        DIVIDE(
            [Total Revenue] - PreviousRevenue,
            PreviousRevenue
        )
    )
\`\`\`

The percentage measure returns a *ratio* and should be formatted as a percentage in Power BI. The first reporting month has no previous month in the dataset and should show a blank change.

**Filter-context note:** These measures are intended for visuals with a month filter. When multiple months are selected, a MoM measure may summarize a period rather than represent the latest month. A separate latest-month measure would be needed for a dedicated top-level growth KPI.

## Channel revenue share

\`\`\`dax
Revenue Contribution % =
DIVIDE(
    [Total Revenue],
    CALCULATE(
        [Total Revenue],
        REMOVEFILTERS('Sales Data'[Channel])
    ),
    0
)
\`\`\`

This removes only the channel filter from the denominator, allowing regional and time selections to remain active. It is **channel share**, not necessarily regional or product share.

## Product revenue ranking

\`\`\`dax
Product Revenue Rank =
RANKX(
    ALLSELECTED('Sales Data'[Product]),
    [Total Revenue],
    ,
    DESC,
    DENSE
)
\`\`\`

Rank 1 represents the highest-revenue product within the selected report context. The ranking can change when channel or region slicers are applied.

## Dynamic title (optional dashboard enhancement)

\`\`\`dax
Dynamic Dashboard Title =
VAR SelectedChannel =
    SELECTEDVALUE('Sales Data'[Channel], "All Channels")
RETURN
    "Retail Sales Performance | " & SelectedChannel
\`\`\`

This can be displayed in a card visual. When zero or multiple channels are selected, the default label is **All Channels**.

## Validation checks

The source workbook contains **500 distinct orders**, **£160,935.05** in revenue, and **£321.87** in average order value, with no missing values or revenue check mismatches.

If results differ after opening the \`.pbix\` file, inspect existing filters, data source paths, date relationships, and currency formatting before assuming a calculation is incorrect.
