# Build the report in Power BI Desktop

1. Open Power BI Desktop.
2. Select **Get data → Text/CSV** and choose `data/customer_data.csv`.
3. Select **Transform Data** and verify types:
   - Dates: `Join Date`, `Last Purchase Date`
   - Whole numbers: `Age`, `Purchase Frequency`, `Engagement Score`, `Satisfaction Score`
   - Decimal/currency: `Average Order Value`, `Total Spend`
   - Text: all ID, category, region, status, segment, and tier fields
4. Remove blank rows and check duplicate `Customer ID`; keep one row per customer.
5. Select **Close & Apply**.
6. Rename the table `customer_data` in the Data pane if needed.
7. Open `docs/DAX_Measures.md`; create each measure via **Modeling → New measure**.
8. Build KPI cards and charts as listed in `README.md`.
9. Format revenue and AOV as currency; retention/churn/repeat rates as percentages.
10. Save the report as `powerbi/Customer_Segmentation_Retention_Analytics.pbix`.
11. Capture a real screenshot of the report page and save it as `screenshots/dashboard-overview.png`.
12. Recheck that slicers filter all relevant visuals, then upload the project folder to a public GitHub repository.

**Important:** Power BI Desktop must be installed on your computer to create/save the `.pbix`. Do not upload a mockup image as if it were a working Power BI report.
