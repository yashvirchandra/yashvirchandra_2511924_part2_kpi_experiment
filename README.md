# Part 2: KPI Framework, Experiment Analysis & Decision Recommendation

# TASK 1:

## Business Context

A subscription-based digital product company launched a new onboarding and activation campaign to improve user conversion and early engagement.

Users were divided into two groups:
- Control Group: Existing onboarding experience
- Treatment Group: New campaign experience

The purpose of this analysis is to determine whether the new campaign should be launched for all users.

## Business Problem

The main decision is whether the company should replace the existing onboarding experience with the new campaign experience. This decision impacts all new users who enter the product onboarding journey. The primary metric that should improve is paid conversion rate because the business goal is to convert more users into paying customers. Along with conversion improvement, the company must monitor risks such as increased refunds, higher support requirements, lower engagement quality, and negative impact on specific user segments. The recommendation will be based on experiment results, statistical evidence, and evaluation of guardrail metrics.

## Evidence Required

Before launching the campaign, we need evidence that:
- Treatment improves the main success metric
- Improvement is statistically meaningful
- User quality is not negatively affected
- No important customer segment performs worse


# TASK 2:

# North Star Metric

## Selected Metric: Paid Conversion Rate

Paid Conversion Rate is selected as the North Star metric because the main objective of the onboarding campaign is to increase the number of users who become paying customers. This metric directly represents business growth because more converted users lead to higher subscription revenue. Other metrics such as landing page visits, trial starts, and onboarding completion are supporting metrics because they represent steps in the customer journey but do not directly measure business value. However, optimizing only paid conversion rate can create problems if users convert but later cancel, request refunds, or create additional support load. Therefore, conversion improvement must be evaluated together with guardrail metrics.


# TASK 4:

## Experiment Analysis Approach

### Data Quality Checks

Missing values were checked across all dataset columns.

The analysis found missing values in device_type (18 records), traffic_source (24 records), days_to_convert (1336 records), and engagement_score (14 records).

No rows were removed because missing days_to_convert values represent users who did not convert and removing them could affect experiment results. Other missing values were retained to preserve the original experiment population.

Duplicate user IDs were checked. 8 duplicate IDs were identified and will be reviewed before final analysis to avoid incorrect user counting.

All binary fields were validated:
- visited_landing_page
- started_trial
- completed_onboarding
- converted_to_paid
- refund_requested

Only valid binary values (0 and 1) were found.

Revenue values were checked for unusual values. Revenue ranged from 0 to 8610.72 with an average revenue of 52.83. No revenue records were removed because extreme values may represent genuine high-value customers.

Segment distribution will be checked across region, device type, and traffic source to ensure fair comparison between Control and Treatment groups.
