# Business Context & Problem Statement (Task 1)

Our company sells a subscription-based digital product and recently tested a new onboarding and activation campaign. The goal was to see if a new onboarding experience could get more users engaged early on and convert them into paying customers. 

To test this, the company set up an A/B test:
- Control Group: Got the old, existing onboarding setup.
- Treatment Group: Got the new campaign onboarding experience.

## The Business Problem

The core decision I need to help make is whether the company should roll out this new onboarding campaign to all incoming users, scrap it, or maybe just launch it for certain user segments. This decision affects every new user signing up. 

While we want the **Paid Conversion Rate** to go up, we also have to watch out for risks. For example, if the new flow forces or tricks users into buying, our refund requests might shoot up, or users might get confused and flood the support team with tickets. We need clear evidence that the new flow genuinely improves paid conversions without ruining our guardrail metrics before recommending a full launch.

---

# North Star Metric Framework (Task 2)

## Selected Metric: Paid Conversion Rate

I chose Paid Conversion Rate (Converted Users / Total Users) as the North Star Metric for this project.

- Why it's the main metric: In a subscription business, getting users to actually pay is what keeps the lights on and drives revenue growth. 
- Why others are just supporting metrics: Metrics like *Landing Page Visit Rate*, *Trial Start Rate*, and *Onboarding Completion Rate* are important to track the user journey, but they don't bring in money. A user could easily finish the onboarding steps but then leave without paying a single rupee. 
- What could go wrong if optimized blindly: If we only look at conversion rates, we might use pushy tactics that get people to convert, but they will end up asking for refunds later or raising too many support tickets, which hurts the business long-term.

---

# KPI Tree Summary (Task 3)

To see how different metrics connect back to our North Star, I broke it down into drivers:
- North Star Metric: Paid Conversion Rate
- Primary Drivers: Funnel Progression (how users move through steps), User Engagement (how much they use the product), and Revenue Quality.
- Sub-Drivers: Landing page clicks, onboarding steps completed, trial starts, and engagement scores.
- Guardrail Metrics: Refund Rate, Support Ticket Rate, and Days to Convert.
(The tree image is saved in the repository at outputs/kpi_tree.png and previewed at screenshots/kpi_tree_preview.png)

---

# Data Preparation & Cleaning Approach (Task 4)

Before doing any math or hypothesis testing, I checked the dataset inside analysis/experiment_analysis.xlsx for any data quality issues. Here is what I found and how I handled it:

1. Missing Values: device_type (18 missing) and traffic_source (24 missing): I decided to keep these rows so I don't lose sample size. I just labeled the blanks as "Unknown".
- engagement_score (14 missing): Kept them as is since it's a very tiny number of rows.
- days_to_convert (1,336 missing): These are blank because those users simply never converted to paid. Leaving them blank is correct; deleting them would ruin the conversion calculation.
2. Duplicate User IDs: I ran a check and found 8 duplicate user IDs in the data. I have noted them down in the analysis notes to keep track of them.
3. Binary Validation: Checked fields like completed_onboarding and converted_to_paid . They all correctly contain only 0 or 1.
4. Revenue Outliers: The revenue goes from 0 up to a maximum of $8,610.72. Even though some numbers are very high, I didn't delete them because some users buy expensive premium or annual plans, which is normal for a business.
5. Segment Check: The distribution looks balanced between Control and Treatment, meaning it's a fair test.
