# Customer Segmentation & Retention Analytics in Power BI

## Objective
Build an interactive business-intelligence dashboard that summarizes customer value, purchase behavior, retention status, and loyalty tiers. The goal is to help marketing, CRM, and growth teams prioritize retention actions using customer-level indicators.

## Dataset
`data/customer_data.csv` contains 300 fictional, synthetic customer records. It includes demographics, join and last-purchase dates, purchase frequency, average order value, total spend, channel, engagement, satisfaction, retention status, customer segment, and loyalty tier. No real customer data is used.

**Important limitation:** this is a customer-level demo dataset (one row per customer), not a transaction ledger. The supplied measures support customer counts, segment revenue comparisons, and status rates. A proper cohort-retention matrix requires transaction-level order history and a defined cohort methodology.

## Tools
- Microsoft Power BI Desktop
- Power Query for cleaning and transformations
- DAX for measures
- CSV dataset
- GitHub for version control and portfolio presentation

## Suggested dashboard layout
1. **Top KPI cards:** Total Customers, Total Revenue, Retention Rate, Churn Rate, Average Order Value.
2. **Middle charts:** Revenue by Customer Segment; customer count by segment; Retention Status distribution; customers by Purchase Channel.
3. **Bottom:** segment/loyalty matrix and a short business-insights text area.
4. **Slicers:** City/Region, Customer Segment, Purchase Channel, Loyalty Tier, Gender, and Join Date.

## Power Query workflow
1. Home → Get Data → Text/CSV → select `data/customer_data.csv`.
2. Choose Transform Data.
3. Set `Customer ID`, `Customer Name`, `Gender`, `City/Region`, `Occupation`, `Income Level`, `Preferred Product Category`, `Purchase Channel`, `Customer Type`, `Retention Status`, `Customer Segment`, and `Loyalty Tier` to Text.
4. Set `Age`, `Purchase Frequency`, `Engagement Score`, and `Satisfaction Score` to Whole Number.
5. Set `Average Order Value` and `Total Spend` to Decimal Number or Fixed Decimal Number.
6. Set `Join Date` and `Last Purchase Date` to Date.
7. Check Customer ID for duplicates; the generated data should have unique IDs. Remove blank rows if any are present.
8. Select Close & Apply.

## Data model
The starter file is a single flat customer table, so no relationships are required. In Model view, confirm date fields are typed as Date. A future enhanced version can separate customers, transactions, and a Date table into a star schema.

## DAX measures
See [`docs/DAX_Measures.md`](docs/DAX_Measures.md). Create each measure using Modeling → New measure. Format revenue and AOV as currency and rates as Percentage.

## Build visuals
- Cards: Total Customers, Total Revenue, Retention Rate %, Churn Rate %, Average Order Value.
- Clustered bar: Customer Segment on Y-axis, Total Revenue on X-axis.
- Column chart: Customer Segment and Total Customers.
- Donut: Retention Status and Total Customers.
- Bar/column: Purchase Channel and Total Revenue.
- Matrix: Rows = Customer Segment; Columns = Loyalty Tier; Values = Total Customers and Total Revenue.
- Slicers: City/Region, Customer Segment, Purchase Channel, Loyalty Tier, Gender, Join Date.

## Professional design
Use a light neutral background, navy titles, corporate blue for primary metrics, green for retained, amber for at-risk, and muted red for churned. Align cards evenly, keep consistent spacing, and use readable fonts. Avoid excessive icons and 3D visuals.

## Business questions to explore
- Which segment contributes the most total spend?
- Which cities have the highest at-risk or churned counts?
- Which channel has the highest revenue in this synthetic sample?
- How does retention status differ by loyalty tier?
- Do engagement and satisfaction scores differ across retention statuses?

Do not state these as findings until you have checked the actual visuals and filtered data. The dataset is synthetic and its patterns are illustrative.

## Screenshots
Save your actual Power BI screenshots in `screenshots/` and embed them below:
<!-- Replace this placeholder after creating the report -->
`![Dashboard overview](screenshots/dashboard-overview.png)`

## Repository structure
```text
Customer-Segmentation-Retention-Analytics/
├── data/
│   └── customer_data.csv
├── docs/
│   └── DAX_Measures.md
├── powerbi/
│   └── (save the finished .pbix report here)
├── screenshots/
│   └── (add real dashboard screenshots here)
├── README.md
└── .gitignore
```

## Limitations and responsible use
This project is a portfolio demonstration using synthetic data, not a validated churn prediction model. Retention Status is generated for demonstration from recency/engagement rules; it should not be interpreted as a prediction for real customers. Use only authorized, privacy-safe data in real business settings.

## Conclusion
This starter project demonstrates data preparation, KPI design, DAX measures, customer segmentation, and dashboard storytelling in Power BI. The `.pbix` file and screenshots should be added after you build and verify the report in Power BI Desktop.
