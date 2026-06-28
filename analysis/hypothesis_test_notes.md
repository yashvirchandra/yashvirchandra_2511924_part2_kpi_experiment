# Hypothesis Test Notes

## Metric Being Tested:

Paid Conversion Rate

(Calculated as: Converted Users / Total Users)

---

## Business Question

Does the new onboarding campaign improve the percentage of users who convert to paid customers compared to the existing onboarding experience?

---

## Reason for Choosing This Metric

Paid Conversion Rate was selected because it is the North Star Metric for this experiment.

For a subscription-based digital product company, converting users into paying customers directly impacts revenue growth and business success.

Other metrics such as landing page visits, trial starts, and onboarding completion rates are supporting funnel metrics. They help explain user behavior but do not directly represent business value unless users become paying customers.

---

## Null Hypothesis (H0)

The new onboarding campaign does not increase the paid conversion rate compared to the current onboarding experience.

Formula: Paid Conversion Rate (Treatment) <= Paid Conversion Rate (Control)

---

## Alternate Hypothesis (H1)

The new onboarding campaign increases the paid conversion rate compared to the current onboarding experience.

Formula: Paid Conversion Rate (Treatment) > Paid Conversion Rate (Control)

---

## Test Type: One-tailed hypothesis test.

A one-tailed test was selected because the business objective is directional. The company wants to determine whether the new onboarding experience performs better than the existing experience.

---

## Significance Level

Alpha = 0.05

This represents a 95% confidence level.

---

## Test Inputs

| Group | Converted Users | Not Converted Users | Total Users |
|---|---:|---:|---:|
| Control | 22 | 671 | 693 |
| Treatment | 50 | 665 | 715 |

---

## Test Method

A Chi-Square Test of Independence was performed.

The Chi-Square test was selected because the experiment compares two categorical groups (Control and Treatment) and evaluates a binary outcome (Converted vs Not Converted).

The test determines whether the difference in conversion rates between groups is statistically significant or could have occurred due to random variation.

---

## Test Result

Test Used:

Chi-Square Test of Independence

- Significance Level: 0.05
- P-value: 0.000383156

---

## Decision Rule

If:

p-value < 0.05

Reject the null hypothesis.

If:

p-value >= 0.05

Fail to reject the null hypothesis.

---

## Decision

Reject H0.

---

## Interpretation

The p-value (0.000383156) is lower than the significance level of 0.05. Therefore, there is statistically significant evidence that the Treatment group has a higher Paid Conversion Rate than the Control group.

---

## Business Interpretation

The new onboarding campaign improved the North Star Metric.

Paid Conversion Rate increased from:
- Control: 3.17%
- Treatment: 6.99%
This indicates that the new onboarding experience successfully improves user conversion. However, the final launch decision should also consider guardrail metrics such as refund rate, support ticket rate, engagement score, days to convert, and revenue quality.
