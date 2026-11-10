# KPI Dictionary — E-Commerce Customer Analytics

This document defines the measures and dimensions presented in the Power BI customer analytics dashboard.

> **Important:** The dashboard screenshot provides displayed values, but not the underlying DAX definitions. The formulas below are recommended business definitions. Confirm the source field name and aggregation logic in the `.pbix` file before treating them as the exact implemented measures.

## 1. Headline KPIs

| KPI | Dashboard value | Recommended definition | Business use |
|---|---:|---|---|
| Total Customers | 25K | Distinct count of `customer_id` | Measures the size of the customer base |
| Average CAC | $42.16 | Total acquisition cost divided by the number of eligible acquired customers, or the agreed average of customer-level CAC | Indicates average acquisition cost per customer |
| Total CAC | $1.05M | Sum of the customer acquisition cost field, if each row represents a cost amount to be summed | Shows total acquisition-cost amount represented in the data |
| Median Customer Age | 46 years | Median of `customer_age` | Describes the midpoint age and is less sensitive to extreme ages |
| Top Performing Segment | Consumer | Segment with the highest customer count in the current filter context | Identifies the largest segment by volume |
| Top Country | USA | Country with the highest customer count in the current filter context | Identifies the largest customer geography |

### Recommended DAX patterns

Use the actual field name from the model. The screenshot truncates the acquisition-cost field name, so replace `[customer_acquisition_cost]` below if the model uses a different name.

```DAX
Total Customers =
DISTINCTCOUNT(customer_master[customer_id])
```

```DAX
Total CAC =
SUM(customer_master[customer_acquisition_cost])
```

```DAX
Average CAC =
AVERAGE(customer_master[customer_acquisition_cost])
```

```DAX
Median Customer Age =
MEDIAN(customer_master[customer_age])
```

The `Average CAC` pattern above is appropriate only if the source column contains a customer-level CAC value and a simple arithmetic average is the intended definition. If CAC is calculated from aggregated acquisition spend and acquired customers, use:

```DAX
Average CAC =
DIVIDE([Total Acquisition Spend], [Acquired Customers])
```

Do not use both definitions interchangeably. The correct formula depends on how the source data defines CAC.

## 2. Analytical Measures and Breakdowns

| Measure / breakdown | Visual location | Interpretation |
|---|---|---|
| Customer count by segment | Segment-wise volume chart | Compares the size of Consumer, Premium, VIP, and Business segments |
| CAC by segment | Segment-wise volume and CAC chart | Compares acquisition-cost values across segments |
| Customers by region | Region-wise customers bar chart | Shows the distribution of customers across regions |
| Customers by country | Country-wise volume donut | Shows country contribution to the customer base |
| CAC by region | Region-wise CAC chart | Compares regional CAC contribution |
| Customers by age group | Age cohort chart and matrix | Shows customer distribution across age bands |
| Average CAC by age group | Age cohort chart | Compares average CAC between age cohorts |
| Average CAC by segment and gender | Treemap | Highlights differences between segment/gender combinations |
| Customer count by gender | Gender donut chart | Shows the gender composition of the customer base |
| Average CAC by customer | Customer ranking bar chart | Compares the displayed customers by average CAC |
| Customer segment key influencers | Key influencers visual | Explores attributes associated with the selected segment outcome |

## 3. Dimensions and Fields

| Field | Analytical role |
|---|---|
| `customer_id` | Customer identifier; use distinct count for customer volume |
| `customer_name` | Customer-level descriptive field |
| `customer_age` | Numeric age field |
| `Age_group` | Age cohort category |
| `gender` | Customer demographic category |
| `customer_segment` | Business/customer segment |
| `customer_city` | City-level geography |
| `customer_state` | State-level geography |
| `customer_country` | Country-level geography |
| `customer_postal_code` | Postal geography |
| `region` | Regional grouping |
| Customer acquisition cost field | Cost metric used in CAC calculations |

## 4. Metric Governance and Validation

Before publishing or using the dashboard for decisions, verify:

1. **Customer grain:** Confirm whether one row represents one customer. If customers can appear multiple times, use `DISTINCTCOUNT(customer_id)` for customer volume.
2. **Customer ID quality:** Check for blank IDs and duplicate records.
3. **CAC definition:** Confirm whether the field is individual customer CAC, allocated acquisition spend, or another cost measure.
4. **CAC aggregation:** Confirm whether summing the field is meaningful. A total of customer-level CAC values is not necessarily the same as total marketing spend.
5. **Average CAC:** Confirm whether a simple average or weighted ratio is required.
6. **Age quality:** Check missing, negative, implausible, and out-of-range ages.
7. **Category consistency:** Standardise segment, gender, country, and region labels.
8. **Filter context:** Confirm that KPI cards and charts respond consistently to slicers.
9. **Rounding:** Reconcile displayed rounded labels against unrounded measure values.
10. **Reconciliation:** Compare dashboard totals with independent calculations from the source dataset.

## 5. Snapshot Values

The following are values visible in the supplied dashboard screenshot:

| Metric | Snapshot |
|---|---:|
| Total customers | 25K |
| Average CAC | $42.16 |
| Total CAC | $1.05M |
| Median age | 46 years |
| Consumer segment | Approximately 13.6K customers |
| Premium segment | Approximately 6.3K customers |
| VIP segment | Approximately 2.5K customers |
| Business segment | Approximately 2.5K customers |
| USA customer share | Approximately 59.7% |
| USA customer count | Approximately 14.93K |

These are rounded visual labels. They should be refreshed from the report and validated against the underlying data before being quoted externally.
