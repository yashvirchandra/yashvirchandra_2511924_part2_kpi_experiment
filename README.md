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
