# DAX Measures (Power BI)

> Table name assumed: `customer_data`. If Power BI names the table differently, update the formulas.

```DAX
Total Customers = DISTINCTCOUNT(customer_data[Customer ID])
```

```DAX
Total Revenue = SUM(customer_data[Total Spend])
```

```DAX
Average Order Value = AVERAGE(customer_data[Average Order Value])
```

```DAX
Retained Customers =
CALCULATE(
    DISTINCTCOUNT(customer_data[Customer ID]),
    customer_data[Retention Status] = "Retained"
)
```

```DAX
At-Risk Customers =
CALCULATE(
    DISTINCTCOUNT(customer_data[Customer ID]),
    customer_data[Retention Status] = "At Risk"
)
```

```DAX
Churned Customers =
CALCULATE(
    DISTINCTCOUNT(customer_data[Customer ID]),
    customer_data[Retention Status] = "Churned"
)
```

```DAX
Retention Rate % = DIVIDE([Retained Customers], [Total Customers], 0)
```

```DAX
Churn Rate % = DIVIDE([Churned Customers], [Total Customers], 0)
```

```DAX
Repeat Customers =
CALCULATE(
    DISTINCTCOUNT(customer_data[Customer ID]),
    customer_data[Purchase Frequency] > 1
)
```

```DAX
Repeat Customer Rate % = DIVIDE([Repeat Customers], [Total Customers], 0)
```

```DAX
High Value Customers =
CALCULATE(
    DISTINCTCOUNT(customer_data[Customer ID]),
    customer_data[Customer Segment] = "High Value"
)
```

```DAX
Average Engagement Score = AVERAGE(customer_data[Engagement Score])
```

```DAX
Basic Customer Lifetime Value = AVERAGE(customer_data[Total Spend])
```

```DAX
Revenue Share % =
DIVIDE(
    [Total Revenue],
    CALCULATE([Total Revenue], ALL(customer_data[Customer Segment])),
    0
)
```

**Note:** This dataset is one row per customer, so `Total Spend` is the customer-level lifetime spend and `Average Order Value` is an average value provided per customer. It is not transaction-level data. For a true monthly cohort retention analysis, a transaction table with one row per order is needed; this starter dataset supports customer-level retention status and segment comparisons but not a valid cohort heatmap by itself.
