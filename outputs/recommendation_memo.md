# KPI Framework, Business Experiment Analysis & Decision Recommendation

## Business Context

The company is a subscription-based digital product company that launched a new onboarding and activation campaign.

The goal of the campaign was to improve early user engagement and increase the number of users who become paying customers.

Users were divided into two experiment groups:

* **Control Group:** Existing onboarding experience
* **Treatment Group:** New onboarding campaign experience

Leadership needs to decide whether the new onboarding campaign should be launched for all users, launched only for selected segments, or not launched.

The decision impacts future users entering the onboarding process.

---

# Business Problem Statement

The main business problem is to determine whether the new onboarding campaign creates a meaningful improvement in user conversion and engagement compared to the existing onboarding experience.

The main metric expected to improve is **Paid Conversion Rate**, because converting users into paying customers directly contributes to subscription revenue and business growth.

However, the decision should not be based only on conversion improvement.

The company must monitor risks such as:

* Increase in refund requests
* Increase in customer support tickets
* Lower customer quality
* Longer conversion journey
* Negative segment-level impact

The recommendation should be based on experiment results, statistical evidence, and guardrail metric evaluation.

---

# Dataset Description

The dataset contains user-level experiment data including:

* User information
* Experiment group assignment
* User segments
* Onboarding activity
* Trial activity
* Conversion status
* Revenue information
* Engagement score
* Support and refund information

The dataset was analyzed to compare Control and Treatment performance.

---

# North Star Metric Selected

## Paid Conversion Rate

Paid Conversion Rate was selected as the North Star Metric.

Formula:

Converted Users / Total Users

## Why this metric was selected

A subscription business depends on converting users into paying customers.

While metrics like landing page visits, trial starts, and onboarding completion show user movement through the funnel, they do not directly create revenue unless users become paying customers.

Paid Conversion Rate connects user behavior with business growth.

## Risk of optimizing only this metric

Optimizing conversion alone may create negative outcomes.

For example, users may convert but later request refunds, require more support, or generate lower revenue value.

Therefore, conversion improvement must be evaluated with supporting and guardrail metrics.

---

# KPI Tree Summary

The KPI tree explains how the North Star Metric is influenced by different business drivers.

## North Star Metric

Paid Conversion Rate

## Primary Drivers

### 1. Funnel Progression

Sub-drivers:

* Landing page visits
* Trial starts
* Onboarding completion

### 2. User Engagement

Sub-drivers:

* Engagement score
* Product activity

### 3. Revenue Quality

Sub-drivers:

* Paying customers
* Revenue generated

## Guardrail Metrics

The following metrics were included to monitor risks:

* Refund Rate
* Support Ticket Rate
* Days to Convert

KPI Tree file:

`outputs/kpi_tree.png`

Preview:

`screenshots/kpi_tree_preview.png`

---

# Experiment Analysis Approach

The experiment analysis compared Control and Treatment groups.

The following checks were performed before analysis:

* Missing values
* Experiment group distribution
* Duplicate user IDs
* Invalid binary values
* Revenue outliers
* Segment distribution across groups

## Data Cleaning Observations

### Missing Values

Missing values were found in:

* Device Type: 18
* Traffic Source: 24
* Days to Convert: 1336
* Engagement Score: 14

Missing records were retained to avoid reducing the experiment sample size.

Missing days_to_convert values were treated as users who did not convert.

### Group Distribution

Control Group:

693 users

Treatment Group:

715 users

The experiment groups were balanced.

### Duplicate User IDs

8 duplicate user IDs were identified.

They were flagged during validation to prevent incorrect user counting during analysis.

### Binary Validation

Binary fields checked:

* visited_landing_page
* started_trial
* completed_onboarding
* converted_to_paid
* refund_requested

All binary fields contained valid values (0 and 1).

### Revenue Outlier Analysis

Revenue was analyzed using the IQR method.

Revenue range:

Minimum Revenue: 0

Maximum Revenue: 8610.72

High revenue values were retained because they may represent genuine high-value customers.

### Segment Distribution

Segment balance was checked across:

* Region
* Device Type
* Traffic Source
* Plan Type

Control and Treatment groups had similar distributions.

---

# Experiment Summary Results

The experiment comparison showed:

| Metric                     | Control | Treatment |
| -------------------------- | ------: | --------: |
| User Count                 |     693 |       715 |
| Landing Page Visit Rate    |  63.64% |    72.59% |
| Trial Start Rate           |  25.11% |    29.09% |
| Onboarding Completion Rate |  15.58% |    21.26% |
| Paid Conversion Rate       |   3.17% |     6.99% |
| Average Revenue Per User   |   51.75 |     53.88 |
| Refund Rate                |      0% |     0.42% |
| Support Ticket Rate        |  14.72% |    24.76% |
| Average Engagement Score   |   57.03 |     62.93 |
| Average Days To Convert    |    8.86 |       6.4 |

Detailed analysis:

`outputs/experiment_summary.xlsx`

---

# Hypothesis Test Summary

The hypothesis test evaluated whether the Treatment group improved Paid Conversion Rate.

## Hypothesis

Null Hypothesis:

Treatment Paid Conversion Rate <= Control Paid Conversion Rate

Alternate Hypothesis:

Treatment Paid Conversion Rate > Control Paid Conversion Rate

## Test Used

Chi-Square Test of Independence

The test was selected because the experiment compares two groups and a binary outcome:

Converted vs Not Converted

## Significance Level

0.05

## Result

P-value:

0.000383156

Since:

p-value < 0.05

The null hypothesis was rejected.

The Treatment group showed a statistically significant improvement in Paid Conversion Rate.

Hypothesis notes:

`analysis/hypothesis_test_notes.md`

---

# Guardrail Metrics Considered

The following guardrail metrics were evaluated:

## Refund Rate

Control:

0%

Treatment:

0.42%

Refund rate increased slightly but remains low.

## Support Ticket Rate

Control:

14.72%

Treatment:

24.76%

Support tickets increased, which may indicate user confusion or additional support requirements.

## Days To Convert

Control:

8.86 days

Treatment:

6.4 days

Users converted faster in the Treatment group.

## Revenue Quality

Average revenue per converted user:

Control:

1630.10

Treatment:

770.41

Although conversion improved, revenue value per converted user decreased.

---

# Final Recommendation

## Recommendation: Launch Only For Selected Segments

The Treatment group significantly improved the North Star Metric.

Paid Conversion Rate increased from:

Control: 3.17%

Treatment: 6.99%

The campaign also improved engagement and reduced conversion time.

However, increased support tickets and lower revenue per converted user create business risks.

Therefore, a controlled rollout is recommended instead of launching to all users immediately.

The company should monitor:

* Conversion rate
* Support tickets
* Refund rate
* Revenue quality

before expanding the campaign.

---

# Assumptions and Limitations

* Missing values were handled without removing users to preserve experiment size.
* Missing conversion time values were treated as non-converted users.
* Duplicate IDs were identified during validation.
* The experiment measures early user behavior and may not represent long-term retention.
* Revenue quality requires additional monitoring after rollout.

---

# Screenshots Included

The repository contains:

* summary_metrics.png
* hypothesis_test_output.png
* kpi_tree_preview.png

All screenshots are stored inside the `screenshots/` folder.
