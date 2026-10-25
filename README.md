<img width="1912" height="1045" alt="DASHBORD" src="https://github.com/user-attachments/assets/7bbdbaeb-44d2-47dc-9073-b9475296a2f0" />


1. Introduction
I analyzed sales profitability data for Goko Group USA for the year 2014. The dataset contains 369 order records with 26 fields including Order Date, Customer Name, Salesperson, Region, Ship City, Product Name, Revenue, Quantity, and Shipping Fee. I performed the entire analysis and visualization in Tableau Desktop and built the dashboard shown above.
2. Objective
My objectives were:
1. To calculate total revenue and identify top-performing salesperson, city, region, and product.
2. To measure sales performance by region, product, salesperson, state, and city.
3. To track regional performance trend across months of 2014.
4. To compare product performance by region and identify customer concentration.
5. To build a single Tableau dashboard that consolidates profitability KPIs for the year.
3. Data Story
Scale: I analyzed 369 orders generating $435,066.16 total revenue in 2014.

Top KPIs I found:
- Top Salesperson: Nancy Freehafer $104,242.34 (104k) - 23.96% of total revenue.
- Best Performing City: New York $67,180.50 (67k) - 15.44% of total.
- Region of the Year: Northern Region (North) $141,680.34 (141k) - 32.56% of total. South $93,848.33, West $91,251.98, East $108,275.51.
- Highest Grossing Product: Coffee $75,486 - 17.35% of total.

Customer Base: I have 22+ customers. Top customer is Company D (New York) $67,180.50, same as best city, followed by Company H $50,208.35 and Company BB $43,713. This shows customer concentration - top 3 customers generate ~37% of revenue.

Product Mix: Coffee $75,486 top, Curry Sauce $69,000 second, Marmalade $41,391 third. Coffee and Curry Sauce together are 33% of revenue.

Regional Mix: North dominates with $141k, followed by East $108k, South $93k, West $91k.
4. Stake-holders
Sales Management & CEO: My top 4 KPI cards (Top Salesperson, Best City, Region of Year, Highest Product) give them instant view of 2014 performance. North region and Nancy Freehafer are clear winners.

Finance Team: My pie chart by Region (West $42,370.88, East $108,275.51, North $141,660.34, South $93,848.33) and pie chart by Customer (Company H 2,172 orders/revenue, Company C 1,487 etc.) show revenue distribution and customer dependency.

Sales Team: My Salespersons' Performance by Revenue treemap - Nancy $104,242.34 biggest box, Anne Larsen $93,848.33 second. Shows performance gap - Nancy sells 2.5x more than Laura Giussani $41,095.01. Useful for target setting and coaching.

Operations & Logistics: My States' Performance by Revenue map - WA $36,839.99, ID $17,204, CA $27,005.38, WI $37,418, IL $41,095.01, TN $43,703, NY $67,180.50, FL bottom - shows geographic revenue spread, helps plan shipping and inventory.

Product Team: My Product Performance by Region bar chart - Coffee longest bar (~75k), Beer shortest (~18k). Shows which product to promote by region.
5. Tools Used
I used only Tableau for the analysis.

I connected sales_dataset.xlsx Sheet1 (369 rows) as Excel source. I created calculated fields:
- Year(Order Date) filtered to 2014.
- Month(Order Date) for Regional Performance Trend.
- Total Revenue = SUM(Revenue).
- Top Salesperson using MAX with FIXED LOD, Best City using similar.
I built visuals: KPI cards using Text marks with color backgrounds, Pie charts for Region and Customer distribution, Horizontal Bar for Product Performance by Region and Performance Metric by Cities, Treemap for Salespersons' Performance by Revenue, Filled Map for States' Performance, and Area/Stacked Area chart for Regional Performance Trend across months.
I assembled dashboard with Tiled layout, left filters for Customer Name, Salesperson, Region, and Top 6 by SUM(Revenue) limit.
6. Pre-Analysis Board
In Data Source tab, I confirmed 369 rows, 26 columns, 0 critical nulls. Revenue SUM $435,066.16 validated. I checked Order Date range - 2014-01-06 to 2014-12-05 (Excel serial 41640 to 42002). I checked dimensions: Region 4 unique (East, North, South, West), Salesperson 8 unique, Ship City 10+, Product 20+, Customer Name 22+.
I identified need to extract Month and Year from Order Date, and create Top N filter for cities.
7. In-Analysis Board
In Tableau Worksheet:
Built Top KPIs using aggregation and sorting - MAX Revenue by Salesperson for Top Salesperson (Nancy F.), MAX Revenue by Ship City for Best City (New York 67k), MAX Revenue by Region for Region of Year (North 141k), MAX Revenue by Product for Highest Product (Coffee 75k).
Built Pie Chart by Region - Region to Color, SUM(Revenue) to Angle, Revenue labels.
Built Product Performance by Region - Product Name to Rows, SUM(Revenue) to Columns sorted descending.
Built Salespersons' Performance by Revenue Treemap - Salesperson to Detail, SUM(Revenue) to Size and Color.
Built States' Performance by Revenue Map - Ship State to map, SUM(Revenue) to label.
Built Performance Metric by Cities - Ship City to Rows, SUM(Revenue) to Columns with Top 6 filter by SUM(Revenue).
Built Regional Performance Trend - MONTH(Order Date) [2014] to Columns, SUM(Revenue) to Rows, Region to Color as Area chart. Observed North peaks in June ($21,873.31 label) and December ~60k.
Validated all KPI numbers matched raw Excel totals.
8. Dashboard
My Tableau dashboard (DASHBORD.png) has 3 layers:

Top Layer - 4 KPI Cards + 2 Pie Charts: Top Salesperson Nancy F. 104k, Best Performing City New York 67k, Region of the year Northern Region 141k, Highest Grossing Product Coffee 75k. Right side: Region pie (North $141,660.34 biggest slice) and Customer pie (Company H 2,172 biggest, Company C 1,487 etc.).

Middle Layer:
- Product Performance by Region: Horizontal bar - Coffee ~75k longest, Beer ~10k shortest.
- Salespersons' Performance by Revenue: Treemap - Nancy Freehafer $104,242.34 biggest dark green box, Andrew Cencini $67,180.50 second.
- States' Performance by Rev.: US map with revenue labels - NY $67,180.50 highest, WA $36,839.99, CA $27,005.38 etc.

Bottom Layer:
- Performance Metric By Cities: Horizontal bar Top 6 - New York $67,180.50 top, Milwaukee $37,418 bottom.
- Regional Performance Trend: Stacked area chart by Month of Order Date 2014 - Revenue on Y-axis, months Jan-Dec on X, North region dominant, peak in December ~60k total, dip in November ~20k. Shows seasonality - Q4 strongest.

Left Filters: Customer Name, Salesperson, Region with (All) checkbox - interactive filtering.
9. Observation
1. North region dominance: North $141,680.34 = 32.6% of total revenue - 30% higher than East $108k. Region of the year clearly.
2. Salesperson concentration: Nancy Freehafer $104,242.34 = 24% of total revenue alone, 6x more than bottom salesperson Jan Kotas $16,350.50. Heavy dependence on top 2 (Nancy + Anne Larsen $93,848.33 = 45.5% of revenue).
3. Product concentration: Coffee $75,486 and Curry Sauce $69,000 = 33% of total revenue. Beer and Mozzarella low - Beer only $18,046.
4. City concentration: New York $67,180.50 = 15.4% of total, same as Company D customer - indicates single customer in NY drives city performance. Top 6 cities = $289k = 66.5% of revenue.
5. Seasonality: Regional Performance Trend shows peaks in June (~46k), October (~47k), December (~60k) and dip in November (~20k). Q4 (Oct-Dec) is strongest quarter, suggesting holiday sales push.
6. Geographic spread: West coast has WA $36,839, CA $27k, but FL also dark green (Miami $50,145) - bicoastal performance, central US (IL, WI, TN) moderate.
10. Recommendation
1. Replicate North region strategy: Since North generates $141k, I should analyze in Tableau what North does differently - salesperson (likely Nancy and Anne), product mix, and apply to South and West which are below $95k.
2. Reduce salesperson dependency risk: Nancy and Anne generate 45% of revenue. I should create training program to upskill middle performers like Andrew Cencini $67k and Mariya Sergienko $42k to reduce key-person risk.
3. Promote high-margin products: Coffee and Curry Sauce are top 2. I should increase inventory and marketing for them, and investigate why Beer ($18k) and Mozzarella underperform - maybe pricing or placement.
4. Focus on Top 6 cities: New York, Portland, Miami, Memphis, Chicago, Milwaukee generate 66% of revenue. I should allocate more sales resources and shipping capacity to these cities.
5. Plan for Q4 peak: December shows ~60k peak. I should prepare inventory in Q3 and run promotions in November dip to smooth revenue.
6. Diversify customer base: Top customer Company D = $67k (15% of total). If this customer leaves, Best City New York collapses. I should acquire more customers in East and West regions.
11. Summary
I used only Tableau to analyze 369 orders from Goko Group USA for 2014, totaling $435,066.16 revenue.
I found North region is the top region with $141,680.34, Nancy Freehafer is top salesperson with $104,242.34, New York is best city with $67,180.50, and Coffee is highest grossing product with $75,486.
My analysis shows heavy concentration - top 2 salespersons generate 45% of revenue, top 2 products generate 33%, and top 6 cities generate 66%. Regional trend shows strong seasonality with Q4 peak.
My Tableau dashboard provides a single-page view to monitor profitability by salesperson, region, city, state, product, and customer for stakeholders, with interactive filters for Customer, Salesperson, and Region.
