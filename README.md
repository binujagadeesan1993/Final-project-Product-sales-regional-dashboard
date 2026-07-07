# Final-project-Product-sales-regional-dashboard
Power BI dashboard and analysis of product sales performance across 5 regions, 7 products, and 2 customer segments (2023–2025), built with Python, NumPy, Matplotlib/Seaborn, and Power BI Desktop.



1.	Project Summary

This project analyses end-to-end product sales performance across five regions, seven product categories, and two customer segments (Retail and Wholesale) over a 30-month period (January 2023 to June 2025). Raw transactional data
— covering order details, pricing, discounts, payment methods, promotions, returns, delivery timelines, and risk flags — was cleaned, structured, and aggregated to support both statistical analysis and interactive business reporting.

The workflow followed a standard analytics pipeline: data cleaning and exploration in Python, statistical summarisation and visual exploration using NumPy, Matplotlib, and Seaborn, and finally the construction of an interactive Power BI dashboard for stakeholder-facing reporting. The resulting dashboard (summarised in this document) enables business users to explore sales trends by region, product, salesperson, payment method, customer type, and store location, while also surfacing operational risk indicators such as return rate and order risk classification.

2.	Tools and Technologies

Python (Google Colab): Used as the core environment for data cleaning, transformation, and exploratory analysis, run in a cloud-based notebook setting for ease of collaboration and reproducibility.
NumPy and libraries for data manipulation: Used for numerical computations, array operations, and structuring the dataset (alongside pandas-style manipulation) ahead of aggregation and visualization.
Matplotlib and Seaborn for visualization: Used to build exploratory statistical charts (trend lines, distributions, comparisons) during the analysis phase, ahead of finalizing visuals in the interactive dashboard.
Power BI Desktop for interactive dashboards: Used to build the two-page interactive dashboard covered in this report, including gauge charts, bar charts, line charts, a donut chart, a treemap, and slicer-based filtering across products, payment methods, and risk factors.

3.	Executive Summary

This report presents an analysis of the Product Sales & Regional Performance Dashboard built in Power BI, based on 1,500 individual sales transactions recorded between January 2023 and June 2025. The dataset spans five regions (Central, East, North, South, and West), seven product categories (Chair, Desk, Laptop, Monitor, Phone, Printer, and Tablet), six salespeople, five payment methods, four promotional campaigns, and two customer segments (Retail and Wholesale).

Overall, the business generated total sales of approximately $4.38 million across the analysis period, at an average order value of $2,919.99. The dataset also captures operational metrics such as delivery performance, shipping cost, and return behaviour, which together provide a rounded view of both sales performance and fulfilment quality. The sections below walk through each visual on the two dashboard pages, followed by a consolidated set of insights and recommendations.

4.	Key Performance Indicators (KPIs)

$4.38M

TOTAL SALES	1,500

TOTAL ORDERS	$2,919.99

AVG ORDER VALUE
24.8%

RETURN RATE	6.04 days

AVG DELIVERY DAYS	$41,260.94

TOTAL SHIPPING COST


These six KPI cards form the control-panel of the dashboard:

Total Sales ($4.38M): The cumulative revenue generated across all 1,500 orders, all regions, and all products over the two-and-a-half-year window.
Total Orders (1,500): The full transaction volume underpinning every chart in the report.
Average Order Value ($2,919.99): A healthy per-order value, useful as a benchmark when evaluating discounting, promotions, and salesperson performance.
Return Rate (24.8%): Roughly 1 in 4 orders is returned, which is materially high and should be treated as a priority operational issue.
Average Delivery Days (6.04): The average time between order date and delivery date, a useful proxy for logistics efficiency.
Total Shipping Cost ($41,260.94): The aggregate cost of fulfilment, relevant when assessing regional or store-level profitability.

5.	Dashboard Page 1 — Customer, Salesperson & Product Overview 

Figure 1: Power BI Dashboard — Customer Overview, Top Performers, Regional Sales Breakdown, Customer Type & Payment Method

5.1	Total Customers (Gauge Chart)

This gauge visual displays the total customer count of 1,500 against a scale of 0 to 3,000, giving an at-a-glance sense of scale relative to a target ceiling. The needle sits at the halfway point of the gauge, which suggests the business has considerable headroom to grow before approaching the upper reference value. Because this number equals the total order count, each row in the dataset is being treated as a unique customer transaction rather than a repeat-purchase count. This visual is best used as a quick orientation metric at the start of any review meeting. It also anchors the “returned customer” figure alongside it, letting viewers immediately relate returns to the overall customer base.

5.2	Returned Customer (Bar Chart)

This single bar shows 372 returned customers, which, when divided by the 1,500 total, produces the 24.8% return rate shown in the KPI card above. Placing this bar directly beside the Total Customers gauge is a deliberate design choice that invites the viewer to compare the two figures instantly. A return rate approaching a quarter of all orders is high for most retail and B2B product categories and typically points to issues such as product quality, inaccurate listings, sizing/fit problems, or delivery damage. This chart is one of the most important visuals on the dashboard from a risk-management perspective, since returns directly erode the $4.38M in recorded sales. Any deep-dive analysis of returns by product, region, or salesperson would materially strengthen this dashboard.

5.3	Top Performers by Sales (Horizontal Bar Chart)

This chart ranks the six salespeople by total sales value: Bob ($0.80M), Alice ($0.79M), Frank ($0.71M), Carlos ($0.71M), Eva ($0.70M), and Diana ($0.68M). The spread between the highest and lowest performer is roughly $120K, which is a relatively narrow band, indicating a fairly even distribution of workload or territory rather than one salesperson dramatically outperforming the rest. Bob and Alice form a clear top tier and could be studied for best practices that might be transferable to the rest of the team. Frank and Carlos are almost tied, which may be worth checking for data entry consistency. This visual is valuable for performance reviews, incentive planning, and identifying coaching opportunities for the lower-ranked reps.
5.4	Product Grid (Slicer Cards)

The seven tiles — Chair, Desk, Laptop, Monitor, Phone, Printer, and Tablet — function as an interactive slicer rather than a chart of values. Clicking any tile filters every other visual on the page to that specific product, allowing a user to instantly see how a single product performs across regions, customer types, and payment methods. This design pattern is common in Power BI dashboards because it turns a static report into an exploratory tool. The even 3-3-1 grid layout keeps the interface tidy and gives each product equal visual prominence, avoiding any implicit ranking bias. Analysts should use this slicer to drill into underperforming products, such as Phone, which has the lowest total sales of the seven categories.

5.5	Regional Sales Breakdown by Product (Horizontal Stacked/Clustered Bar Chart)

This chart breaks down the sum of TotalPrice by product on the vertical axis, with each bar segmented by region (Central, East, North, South, West) shown in different shades. Tablet, Printer, and Laptop are the strongest-performing products overall, each generating roughly $680K or more across all regions combined, while Phone and Desk trail behind. The chart makes clear that no single region dominates every product; instead, regional strength varies by category, for example North performs particularly well for Desk and Monitor. This visual is the most information-dense chart on the page and is best read alongside the Total Sales KPI to understand what proportion of overall revenue each product-region combination contributes. It is a strong candidate for adding data labels or a total-sales sort order to speed up interpretation.





5.6	Average of TotalPrice by Customer Type (Bar Chart)

This chart compares the average order value between Retail ($3.0K) and Wholesale ($2.9K) customers. The two figures are close, indicating that, on a per-order basis, Wholesale customers are not securing materially larger average baskets despite typically being expected to buy in bulk. This is a useful sanity check on pricing and discount strategy, since a much larger gap would normally be expected if wholesale pricing tiers were functioning as intended. The near-parity between the two customer types suggests that either wholesale order sizes are smaller than typical for the sector, or that retail customers are purchasing higher-value individual items. This chart is a good candidate for further segmentation by product category to see where the customer types diverge most.

5.7	Sales Breakdown by Payment Method / Customer Type (Donut Chart)

This donut chart splits total sales into Retail ($2.18M, 49.87%) and Wholesale ($2.2M, 50.13%), an almost perfectly even 50/50 split of the $4.38M total. Despite the panel title referencing “Payment Method,” the legend and slice labels reflect the CustomerType field, so the visual should be re-labelled or re-titled in the underlying report to avoid confusion for future readers. The near-equal split between the two customer segments indicates a well-balanced revenue base that is not overly dependent on either retail or wholesale demand, which is generally a healthy sign of business resilience. This balance also means strategic decisions, such as promotional targeting or credit terms, need to weigh both segments roughly equally rather than favouring one. Renaming this visual accurately would improve the overall credibility of the dashboard.                                       




6.	Dashboard Page 2 — Payment Trends, Risk & Store Distribution
 
                  
6.1	Sales Trend by Payment Method and Region, 2023–2025 (Multi-Line Charts)

This is actually a set of four line charts — one each for Cash, Credit Card, Debit Card, and Gift Card — plotting the sum of TotalPrice by year (2023, 2024, 2025) with a separate coloured line for each of the five regions. Across all four payment methods, sales generally peak in 2024 before softening into 2025, which may reflect either genuine demand seasonality or the fact that the 2025 data only runs through June and is therefore a partial year. Credit Card shows the widest swings between regions, with one region spiking above $90K in 2024 before falling sharply, while Gift Card and Debit Card trends are comparatively more stable across regions. Because each mini-chart uses a different y-axis scale, the four panels should be compared directionally rather than by absolute value at a glance. This set of charts is best used to spot which payment methods are gaining or losing share by region over time and to inform where marketing or promotional spend might be redirected.

6.2	PaymentMethod (Slicer Cards)

The five tiles — Cash, Credit Card, Debit Card, Gift Card, and Online — again act as an interactive slicer rather than a chart, letting a user isolate a single payment method and see its effect ripple through the rest of the report page. From the underlying data, Online ($971K) and Cash ($950K) are the two leading payment methods by total sales, followed by Gift Card, Credit Card, and Debit Card. This slicer is particularly useful when combined with the line charts above it, since
selecting one payment method will filter those four line panels down to a single, larger trend line for deeper inspection. The layout keeps all five payment options equally visible, which is good practice for slicers used in executive-facing dashboards. Adding total-sales values directly onto these tiles would make the grid more informative even before any filtering is applied.

6.3	Risk_Factor (Slicer Cards)

This simple two-tile slicer — No Risk and Risk — allows the user to filter the entire page by the order-level risk flag captured in the dataset. Aggregating the underlying Risk_Region data shows that roughly three-quarters of orders across every region fall into the No Risk category, with the remaining quarter flagged as Risk, a proportion that is remarkably consistent across Central, East, North, South, and West. This consistency suggests the risk factor is being driven by a systemic process (such as payment verification or fraud scoring rules) rather than by any single region's customer base or salesperson. Because this ratio closely tracks the 24.8% overall return rate, it is worth investigating whether flagged “Risk” orders are also the orders most likely to be returned. This slicer would benefit from a small supporting chart (for example a stacked bar of Risk by Region) placed directly beside it so the proportions are visible without needing to click through the filter.

6.4	Sales Distribution by Product and Store Location (Treemap)

This tree map sizes and colors rectangles by product (Tablet, Printer, Chair, Desk, Laptop, Phone, Monitor) and further subdivides each product block by store location (Store A through Store D), with the sum of TotalPrice driving both size and shading intensity. Tablet and Printer occupy the largest area on the treemap, confirming their position as the two top-selling products identified earlier in the regional breakdown chart. Within each product, the four stores are reasonably close in size, though the tooltip example shown (Monitor, Store A, $148,425.65) illustrates how a user can hover over any tile to retrieve an exact figure. The treemap format is particularly effective here because it lets viewers judge relative scale visually across 28 product-store combinations at once, something a standard bar chart could not do without becoming unreadable. This visual is best used to identify underperforming store-product pairings, such as any noticeably small tiles, which may warrant inventory or merchandising review.
7.	What This Dataset Tells Us

Taken as a whole, this dataset describes a mid-sized, multi-region retail and wholesale operation selling seven office/electronics-related product lines through five payment channels, supported by a six-person sales team and a four- region store network. The data covers a continuous 30-month window (January 2023 to June 2025), which is long enough to observe genuine seasonal and year-over-year patterns rather than short-term noise.

Revenue is broad-based, not concentrated: no single region, product, or salesperson accounts for a disproportionate share of the $4.38M total, and the Retail/Wholesale split is almost perfectly even at 50/50. North is the leading region overall, while Tablet, Printer, and Laptop are the strongest product categories; Phone consistently underperforms across most cuts of the data.
Online and Cash are the two most-used payment methods, together accounting for close to 44% of total sales, which may reflect either channel convenience or promotional bias toward these methods.
Sales performance across the six-person sales team is fairly even, suggesting territories or accounts are reasonably well balanced, though Bob and Alice are consistently the top two performers.
Returns (24.8%) and Risk-flagged orders (~25%) track each other closely across all five regions, hinting that a shared underlying process links order risk scoring to eventual returns — a relationship worth formally testing.
Delivery performance (6.04 days average) and shipping cost ($41,260.94 total) are both moderate and stable, suggesting logistics is not currently a primary driver of the elevated return rate, though it should not be ruled out without further analysis.

8.	Recommendations

•	Investigate the 24.8% return rate immediately — it is the single biggest risk to future revenue.
•	Add a review process to track product damage, so damaged items can be identified and addressed at the source.
•	Track customer feedback by product to help identify and reduce the root causes of the risk factor.
•	Add GPS tracking for dispatch vehicles and CCTV footage of packing areas, to improve visibility into product handling and reduce returns caused by mishandling.
•	Conduct monthly warehouse audits at each location, with a checklist to verify whether materials are in good condition or damaged, checked periodically.
•	Track delivery days for each product and monitor storage conditions at every hub or warehouse via footage, to ensure materials remain in safe condition throughout transit.






