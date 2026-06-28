# Recommendation Memo

## Business Problem Summary

The company launched a new onboarding and activation campaign to improve user conversion and early engagement.

Users were divided into two groups:

**Control Group:** Existing onboarding experience
**Treatment Group:** New campaign experience

Leadership needs to decide whether the new onboarding campaign should be launched for all users, kept for selected segments, or not launched.

The decision impacts future users who go through the onboarding process.

---

## Objective

The main objective is to determine whether the new onboarding campaign improves business performance compared to the existing onboarding experience.

The primary success metric for this experiment is **Paid Conversion Rate** because converting users into paying customers directly contributes to subscription revenue and business growth.

---

## Experiment Result Summary

The experiment was performed using:

Control Group: 693 users
Treatment Group: 715 users

The Paid Conversion Rate results were:

Control: 3.17%
Treatment: 6.99%

The Treatment group showed a significant improvement in paid conversions compared to the Control group.

Other funnel metrics also improved:

* Landing page visit rate increased from 63.64% to 72.59%
* Trial start rate increased from 25.11% to 29.09%
* Onboarding completion rate increased from 15.58% to 21.26%

This indicates that the new onboarding experience improves user movement through the conversion funnel.

---

## Hypothesis Test Interpretation

A Chi-Square test was performed to compare Paid Conversion Rate between the two groups.

Null Hypothesis:
The Treatment group does not improve paid conversion rate compared to Control.

Alternate Hypothesis:
The Treatment group improves paid conversion rate compared to Control.

Significance Level: 0.05

P-value: 0.000383156

Since the p-value is lower than 0.05, the null hypothesis was rejected.

The result provides statistical evidence that the new onboarding campaign improves paid conversion.

---

## Guardrail Analysis

The recommendation was not based only on conversion improvement. Additional metrics were checked to identify possible risks.

### Refund Rate

Control: 0%
Treatment: 0.42%

Refund rate increased slightly in Treatment but the impact is currently low.

### Support Ticket Rate

Control: 14.72%
Treatment: 24.76%

Support tickets increased in the Treatment group. This may indicate that some users are experiencing confusion or require additional help with the new onboarding flow.

### Days to Convert

Control: 8.86 days
Treatment: 6.4 days

Treatment users converted faster, which is a positive signal.

### Revenue Quality

Average revenue per converted user:

Control: 1630.10
Treatment: 770.41

Although more users converted, revenue per converted user decreased. This means the company should monitor whether new conversions are generating similar customer value.

---

## Segment-Level Insight

Segment distribution was checked across:

* Region
* Device Type
* Traffic Source
* Plan Type

The Control and Treatment groups had similar user distributions, which indicates that the experiment results are not heavily affected by segment imbalance.

---

## Final Recommendation

**Recommendation: Launch only for selected segments**

The new onboarding campaign successfully improves the North Star Metric, Paid Conversion Rate, and users reach conversion faster.

However, the increase in support ticket rate and decrease in revenue per converted user create risks that should be monitored.

A controlled rollout is recommended instead of immediately launching for all users.

---

## Risks and Limitations

* The experiment may not capture long-term customer retention impact.
* Higher conversion does not always mean higher customer quality.
* Increased support requirements may affect operational costs.
* Revenue quality should be monitored after rollout.

---

## Next Steps

1. Launch the campaign for selected user segments.
2. Monitor conversion, refunds, support tickets, and revenue quality.
3. Analyze long-term customer value after more data is collected.
4. Expand rollout if results remain positive.
