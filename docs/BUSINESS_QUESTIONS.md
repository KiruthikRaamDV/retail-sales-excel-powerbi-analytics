# Business questions, findings and follow-up investigations

This is the story behind the visuals: **what the dataset shows, what that might mean, and what we would still need to know in a real retail business**.

All numbers are from the **500-row synthetic practice dataset**. They are not results from a real retailer.

| Question | What I found | What I'd investigate next |
| --- | --- | --- |
| Which channel generates more revenue? | Online: **£83,074.70** (51.62%) vs In-store: **£77,860.35** (48.38%). | Is the difference consistent across products, regions, and seasons? |
| Which channel processes more orders? | In-store: **263** vs Online: **237**. | Are store visits or promotions driving order volume? |
| Why is Online AOV higher? | Online AOV: **£350.53** vs In-store: **£296.05**. | Product mix, pricing and item value—not just order count. |
| Do Online customers buy more units per order? | **No**: Online **2.03**, In-store **2.11**. | Compare which items are purchased in each channel. |
| Which month is the strongest? | **May: £20,319.90**. | Were there campaigns, stock changes, or demand shifts? |
| Which month is weakest? | **April: £14,219.05**, followed by **+42.91% MoM** in May. | Review more months and operational events; don't infer a seasonal effect from nine months. |
| Which region leads? | **Leeds: £44,122.00**. | Compare store coverage, costs, traffic and average basket value. |
| Which category drives more revenue? | **Electronics: £123,611.25** vs Accessories: £37,323.80. | Compare margin and inventory before prioritizing category investment. |
| Which product drives the most revenue? | **Laptop: £58,045.00** (36.07% of revenue). | Assess dependence, availability and profit margins. |
| Is most frequently ordered the same as most valuable? | **No**: Monitor appears in 59 orders, Laptop in 39, yet Laptop earns more revenue. | Compare revenue, order frequency and units sold before making decisions. |

## Three management conversations this dashboard can start

### 1. AOV versus order volume

In-store processed more orders but brought in less revenue. I would not immediately recommend discounting or upselling. First I'd investigate **what goes into each basket**, whether prices differ by channel, and how product mix changes between Online and In-store.

### 2. The April-to-May rebound

May's sales increased sharply after April. That's an observation, not a causal explanation. In a real business, I would request promotional calendars, stock information, and a longer sales history to understand why.

### 3. The role of laptops

Laptops generated over a third of revenue. That may be valuable, but it might also mean sales are concentrated in one high-priced item. A useful next step would be to compare **gross margin, stockouts, returns and supplier risk**, which this practice dataset doesn't include.

## Limits of interpretation

- The dataset is synthetic.
- There are no customer IDs for retention or cohort analysis.
- There are no costs, so **profit** cannot be calculated.
- There are no marketing or inventory records to explain changes.
- Only January–September 2026 is represented.
- The first 12-order Excel exercise and the larger 500-order exercise are **different datasets**; their totals should not be combined.

A dashboard should clarify the facts and make it easier to identify **the next question worth asking**.
