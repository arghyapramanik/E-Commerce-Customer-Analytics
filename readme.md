# E-Commerce Customer Analytics Dashboard

An interactive Power BI dashboard for exploring customer distribution, acquisition-cost patterns, and customer characteristics across segments, regions, countries, age groups, and gender.

> **Project type:** Business Intelligence / Customer Analytics  
> **Tool:** Microsoft Power BI  
> **Data model table shown:** `customer_master`  
> **Status:** Dashboard developed; documentation prepared from the current dashboard and field-list screenshots.

## Dashboard Preview

![E-Commerce Customer Analytics Dashboard](Screenshots/ecommerce_customer_analytics.png)

The dashboard brings together customer-volume and customer-acquisition-cost (CAC) views in one report. It is designed to help a business user understand where customers are concentrated, how customer segments compare, and how CAC varies across customer groups and geographies.

## Business Objectives

- Monitor the overall customer base and customer acquisition cost.
- Compare customer volume and CAC across customer segments.
- Understand geographic distribution by region, state, and country.
- Examine customer composition by age group and gender.
- Identify customer groups and locations that may warrant further investigation.
- Provide an interactive reporting view for exploratory business analysis.

## Dashboard Contents

| Dashboard area | What it shows |
|---|---|
| KPI cards | Total customers, average CAC, total CAC, median customer age, top-performing segment, and top country |
| Segment analysis | Customer volume by segment alongside CAC |
| Regional customer analysis | Customer counts by region |
| Country distribution | Country-wise customer volume and share |
| State-level view | Geographic distribution with segment/CAC context |
| Age cohort analysis | Customer volume and average CAC by age group |
| Regional CAC | CAC contribution by region |
| Segment and gender analysis | Average CAC across segment/gender combinations |
| Gender analysis | Customer count by gender |
| Customer-level comparison | Average CAC by customer in the displayed ranking |
| Key influencers | Exploratory factor analysis of the selected customer-segment outcome |

## Tools and Methods

- **Power Query:** Data preparation and transformation before loading the model.
- **DAX:** Measures and calculations used for KPI cards and analytical visuals.
- **Power BI visuals:** Cards, clustered/stacked charts, donut charts, treemap, map, matrix/table, decomposition-style/key-influencer analysis, and slicers.
- **Data fields visible in the model:** `customer_id`, `customer_name`, `customer_age`, `Age_group`, `gender`, `customer_segment`, `customer_city`, `customer_state`, `customer_country`, `customer_postal_code`, `region`, and a customer-acquisition-cost field.

The report uses the `customer_master` table shown in the Power BI Fields pane. The exact source, refresh date, and detailed transformation steps should be added once confirmed.

## Headline Dashboard Snapshot

The values below are read from the current dashboard screenshot and should be treated as a point-in-time snapshot, not as independently audited results.

| KPI | Displayed value |
|---|---:|
| Total customers | 25K |
| Average CAC | $42.16 |
| Total CAC | $1.05M |
| Median customer age | 46 years |
| Top-performing segment by customer volume | Consumer |
| Top country by customer volume | USA |

### Selected observations

- The Consumer segment is the largest segment by customer volume, at approximately 13.6K customers in the displayed visual.
- The USA accounts for approximately 14.93K customers, or 59.7% of the country-wise total shown.
- The regional customer chart shows South as the largest region by customer count in the displayed report.
- Average CAC across the displayed age cohorts is relatively close, ranging from approximately $41.69 to $42.35.
- The regional CAC visual shows South with the largest displayed CAC contribution (approximately $337.71K).

See [`KPI_Dictionary.md`](KPI_Dictionary.md) for KPI definitions and [`Business_Intelligence.md`](Business_Intelligence.md) for interpretation and follow-up questions.

## Repository Structure

```text
power-bi-business-analytics/
├── README.md
├── BigMart-Sales-Analytics/       # Replace with your actual project folder name if different
│   ├── Customer_Analytics.pbix    # Add the Power BI report file
│   └── Screenshots/
│       └── ecommerce_customer_analytics.png
├── KPI_Dictionary.md
└── Business_Intelligence.md
```

Update the file and folder names above to match the actual repository before publishing.

## How to Explore

1. Open the `.pbix` report in Power BI Desktop.
2. Use available slicers and visual interactions to filter customer groups.
3. Compare customer volume with CAC across segments and regions.
4. Review the KPI dictionary to understand the intended meaning of each metric.
5. Use the business intelligence notes as prompts for further investigation.

## Data and Interpretation Notes

- `K` means thousand and `M` means million in the dashboard labels.
- CAC is interpreted as customer acquisition cost, based on the field name and dashboard labels. Confirm the source data's business definition before using it for financial decisions.
- A high total CAC may reflect a larger customer base as well as a higher acquisition cost per customer. Compare total CAC with average CAC and customer volume together.
- The dashboard is descriptive and exploratory. It does not, by itself, establish causation or prove that a segment or region is more profitable.
- Geographic maps and customer rankings should be interpreted in light of data completeness, postal-code quality, and the selected filters.
- Values are rounded in visuals; small differences may occur between chart labels and underlying calculations.

## Future Improvements

- Add a clear reporting-period or data-refresh indicator.
- Document the source, row count, data types, and Power Query transformation steps.
- Add a data-quality page covering missing values, duplicate customer IDs, invalid ages, and CAC outliers.
- Add period-over-period comparisons if a reliable date field is available.
- Add a metric definition for CAC that states exactly which costs are included and the time period to which they relate.
- Validate customer counts using distinct customer IDs and reconcile total CAC to the underlying rows.

## Author

**Arghya Pramanik**  
B.Tech, Computer Science and Business Systems  
GitHub: [arghyapramanik](https://github.com/arghyapramanik)  
LinkedIn: [arghya-pramanik](https://www.linkedin.com/in/arghya-pramanik)
