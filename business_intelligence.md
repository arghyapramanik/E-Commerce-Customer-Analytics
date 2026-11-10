# Business Intelligence — E-Commerce Customer Analytics

## 1. Executive Summary

The Power BI dashboard provides a consolidated view of a 25K-customer dataset, combining customer-volume analysis with customer acquisition cost (CAC). It allows users to compare customer segments, geographic markets, age cohorts, and gender groups.

The current dashboard snapshot displays:

- **25K** total customers.
- **$42.16** average CAC.
- **$1.05M** total CAC.
- **46 years** median customer age.
- **Consumer** as the largest customer segment by volume.
- **USA** as the largest country by customer volume.

These are descriptive findings from the current report view. They do not establish profitability, campaign effectiveness, or causation.

## 2. Key Findings from the Dashboard

### 2.1 Customer segment distribution

The segment-wise chart shows Consumer as the largest segment at approximately 13.6K customers, followed by Premium at approximately 6.3K. VIP and Business each account for approximately 2.5K customers.

**Business interpretation:** The customer base is concentrated in the Consumer segment. This makes Consumer an important group for understanding overall customer behaviour. However, volume alone does not show which segment has the highest lifetime value, retention, or profitability.

**Questions to investigate:**
- Does the Consumer segment also have the highest revenue?
- Do Premium, VIP, or Business customers generate greater value per customer?
- Are acquisition costs justified by retention and lifetime value in each segment?

### 2.2 Geographic distribution

The country-wise chart identifies the USA as the largest market, with approximately 14.93K customers (59.7% of the displayed total). The UK is the next-largest visible contributor at approximately 3.7K (14.8%), followed by Germany at approximately 2.05K (8.18%), Canada at approximately 1.28K (5.12%), and Australia at approximately 1.04K (4.16%).

The region-wise customer chart shows South as the largest region in the current report view.

**Business interpretation:** The customer base is geographically concentrated, particularly in the USA. This may make country-level segmentation useful for regional reporting and market analysis. Customer count alone does not establish market attractiveness.

**Questions to investigate:**
- Does the USA also lead in revenue, margin, and customer retention?
- Are CAC levels materially different between countries?
- Are smaller markets growing, or do they have higher customer value?

### 2.3 Regional CAC

The regional CAC visual displays the following approximate contribution:

| Region | Displayed CAC | Share of displayed total |
|---|---:|---:|
| South | $337.71K | 32.04% |
| Central | $225.96K | 21.44% |
| West | $200.18K | 19.01% |
| East | $162.01K | 15.37% |
| North | $128.13K | 12.16% |

**Business interpretation:** South has the largest displayed CAC contribution. This should not automatically be interpreted as inefficient acquisition. A region with more customers or greater acquisition activity may naturally have a larger total CAC.

**Recommended next analysis:** Compare regional total CAC with customer count, average CAC, revenue, and customer lifetime value. This would help distinguish scale effects from acquisition-cost efficiency.

### 2.4 Age cohort analysis

The age-cohort chart shows a relatively even customer distribution across the four displayed groups:

| Age group | Customer share shown | Average CAC shown |
|---|---:|---:|
| 18–25 | 24.8% | $41.69 |
| 26–35 | 25.1% | $42.19 |
| 36–50 | 24.9% | $41.86 |
| 51+ | 25.2% | $42.35 |

**Business interpretation:** Customer volume is distributed quite evenly across the displayed age groups. Average CAC also appears relatively similar, ranging from about $41.69 to $42.35.

The 51+ cohort has the highest displayed average CAC, while the 18–25 cohort has the lowest. The difference is small in this snapshot and should not be treated as statistically or commercially significant without further analysis.

### 2.5 Gender and segment analysis

The gender distribution visual shows approximately 12.05K Female customers, 11.98K Male customers, and 0.98K Non-Binary customers.

The segment-and-gender treemap compares average CAC across combinations of customer segment and gender.

**Business interpretation:** The displayed customer distribution is broadly balanced between Female and Male categories, while the Non-Binary category represents a smaller group in this dataset. The treemap can help identify differences in average CAC across segment/gender combinations.

**Caution:** Small groups can produce unstable averages. Always consider group size alongside average CAC, and avoid drawing conclusions about individuals from aggregated demographic patterns.

### 2.6 Customer-level CAC comparison

The customer ranking chart compares average CAC for selected customer names.

**Business interpretation:** This view can help locate unusually high or low customer-level CAC values for investigation. It should be used as a diagnostic view, not as a customer performance ranking. Confirm that customer-level CAC is a meaningful measure and that the visual is sorted and filtered as intended.

### 2.7 Key influencers

The Key Influencers visual currently explores factors associated with the selected `customer_segment` outcome. The screenshot indicates an association involving the 51+ age group and the Business segment.

**Business interpretation:** This is an exploratory statistical visual, not proof that age causes segment membership. Review the sample size, available predictors, category balance, and model settings before drawing conclusions.

## 3. Potential Business Recommendations

These are recommendations for further investigation, not conclusions proven by the current dashboard.

1. **Prioritise segment-level value analysis:** Compare revenue, retention, repeat purchase rate, and lifetime value across Consumer, Premium, VIP, and Business segments.
2. **Investigate regional acquisition efficiency:** Compare average CAC and total CAC with customer volume and revenue by region.
3. **Monitor geographic concentration:** Track whether the USA's share of customers changes over time and compare it with market-level value.
4. **Evaluate age cohorts using outcome metrics:** Add retention, conversion, and revenue measures before changing acquisition strategy by age group.
5. **Review high-CAC outliers:** Investigate customers or groups with unusually high CAC after validating the calculation and sample size.
6. **Add time-based monitoring:** If acquisition or transaction dates are available, introduce monthly trends and period-over-period comparisons.



## 4. Limitations

- The current dashboard screenshot does not show a reporting date range or refresh timestamp.
- The source dataset's origin and acquisition-cost definition have not yet been documented.
- The dashboard appears to be based on a customer master table; transaction-level revenue, retention, and lifetime-value analysis may require additional data.
- Rounded labels prevent exact reconciliation from screenshots alone.
- Geographic and demographic relationships are descriptive and should not be interpreted as causal.
- The Key Influencers visual requires validation of its target, predictors, and sample sizes.

## 5. Next Steps

1. Confirm the exact CAC field name and business definition.
2. Document the Power Query transformations and DAX measures actually used.
3. Validate distinct customer counts, duplicate IDs, missing values, and CAC totals.
4. Add a data-quality or validation page.
5. Add time-based and customer-value metrics if supporting data is available.
6. Refresh screenshots after final formatting and validation.

## Conclusion

The dashboard provides a useful overview of customer composition and acquisition-cost distribution across segments, regions, countries, age groups, and gender. Its main strength is bringing multiple customer dimensions into one interactive Power BI report. The next step is to connect these descriptive metrics to revenue, retention, and customer lifetime value so that the analysis can support stronger business decisions.
