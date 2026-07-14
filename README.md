# 🛍️ Customer Behavior Segmentation & Interactive Power BI Dashboard

## 📌 Project Overview
This project analyzes 12 months of behavioral data from 49,381 users of a multinational e-commerce platform to segment customers based on engagement patterns, and to quantify how churn risk and customer value differ across those segments.

The project follows a complete data analytics workflow: data cleaning, exploratory & correlation analysis, unsupervised clustering (K-Means) in Python, and an interactive Power BI dashboard — ending with dollar-quantified, decision-ready retention recommendations.

## 🎯 Business Problem
The platform currently lacks a clear, data-driven answer to the following:

- Are all users equally likely to churn, or are there identifiable behavioral segments with meaningfully different churn risk?
- Do these segments also differ in customer value (Lifetime Value), or is churn risk unrelated to revenue contribution?
- Which segment should be prioritized for retention investment to protect the most revenue at the lowest cost?
- Can segment membership be explained by demographic factors (age, tenure, country), or is it purely behavioral?

Without this segmentation, retention budget risks being spent evenly across all users — including low-value users unlikely to churn, while high-risk, high-value users receive no targeted attention.

## 🎯 Project Objectives
- Clean and prepare 12 months of user behavioral data for analysis.
- Segment users into behavioral tiers using unsupervised clustering (K-Means), validated with the Elbow Method and Silhouette Score.
- Quantify churn rate and Lifetime Value for each segment.
- Determine whether demographic attributes explain segment membership.
- Translate the segmentation into specific, actionable retention recommendations.
- Build an interactive Power BI dashboard for ongoing monitoring.

## 📂 Dataset
The dataset contains approximately 49,000 customer records with behavioral, demographic, and purchasing information.

### Main Features

|       Category       |                       Variables                            |
|----------------------|------------------------------------------------------------|
| User Activity        | Login Frequency, Session Duration Avg, Pages Per Session   |
| Purchasing           | Total Purchases, Average Order Value, Lifetime Value       |
| Engagement           | Email Open Rate, Mobile App Usage, Social Media Engagement |
| Retention            | Churned, Days Since Last Purchase                          |
| Customer Information | Age, Gender, Country, Membership Years                     |
| Shopping Behavior    | Cart Abandonment Rate, Wishlist Items, Discount Usage Rate |

## 🧹 Data Cleaning

- ✅ Checked missing values across all columns — 12 of 24 columns had missing data, ranging from 0.3% (Customer_Service_Calls) to 12% (Social_Media_Engagement_Score); no column exceeded 15%, so all rows were retained.
- ✅ Applied a tiered imputation strategy based on missing severity:
  <5% missing → global median
  5–10% missing → median within a relevant behavioral group (e.g., Discount_Usage_Rate by Membership_Tier), to preserve within-segment       patterns
  >10% missing → group median + a missing-indicator flag column, in case missingness itself is informative
- ✅ Removed invalid records rather than statistical outliers: Age outside 12–90, negative Total_Purchases, and Cart_Abandonment_Rate above 100%.
- ✅ Trimmed the top 1% of Average_Order_Value to prevent extreme values from distorting aggregate metrics.
- ✅ Verified no missing values remained after imputation.

##📊 Exploratory & Clustering Analysis

Correlation Analysis

- Login_Frequency, Session_Duration_Avg, Total_Purchases, and Lifetime_Value are positively correlated with one another, while Cart_Abandonment_Rate is negatively correlated with all of them — confirming a consistent underlying "engagement" signal across metrics.


Clustering — Elbow Method & Silhouette Validation

- K-Means was applied on 3 standardized behavioral features: Login_Frequency, Session_Duration_Avg, and Total_Purchases.
- The Elbow Method pointed to k=3 as the natural cluster count.
- Silhouette scores were compared across k=2–5: k=2 = 0.447, k=3 = 0.350, k=4 = 0.289, k=5 = 0.290. While k=2 scored highest, k=3 was retained because it produces three distinct, business-actionable engagement tiers rather than a single broad active/inactive split — a deliberate trade-off of marginal statistical separation for retention-strategy relevance.

Behavioral & Demographic Profiling

- The three segments show clear separation in behavior: Low Activity (20,363 users, 41.2%) averages 5.1 logins/week and 8.1 purchases; Moderately Active (19,900 users, 40.3%) averages 13.4 logins and 14.0 purchases; High Activity (9,118 users, 18.5%) averages 22.5 logins and 22.5 purchases.
- Age (37.7–37.8 years), Membership_Years (~3 years), and Country distribution show virtually no variation across segments — engagement level cannot be explained by demographics and must be identified through behavioral tracking rather than static profile data.


## 👥 Customer Segmentation

Customers were segmented using K-Means Clustering based on:
- Login Frequency
- Session Duration Average
- Total Purchases

Three customer segments were identified:

|         Segment         |                      Description                       |
|-------------------------|--------------------------------------------------------|
| High Activity Users     | Highly engaged customers with high purchasing activity |
| Moderately Active Users | Average engagement and purchasing behavior             |
| Low Activity Users      | Low engagement and highest churn risk                  |

## 📊 Dashboard Preview

<img width="4775" height="4464" alt="Customer-Behavior-Segmentation_page-0001" src="https://github.com/user-attachments/assets/bba1880f-2445-4dde-a8a1-15216c693638" />


## 💡 Key Insights

Churn & Lifetime Value by Segment

|     Segment       |  Users   |  % of Base  |  Churn Rate  |  Avg. Lifetime Value  |  Avg. Cart Abandonment  |
|-------------------|----------|-------------|--------------|-----------------------|-------------------------|
|   Low Activity    |  20,363  |    41.2%    |    39.88%    |        $889.75        |           68            |
| Moderately Active |  19,900  |    40.3%    |    21.29%    |        $1,546.83      |           55            |
|   High Activity   |   9,118  |    18.5%    |    19.65%    |        $2,341.77      |           38            |

- Churn risk is heavily concentrated in the Low Activity segment — nearly double the churn rate of High Activity users, and this is also the platform's largest segment by user count.
- Lifetime Value scales directly with engagement: a 2.6x gap exists between the lowest and highest segment, showing that the highest-risk segment is also the lowest-value segment per user — but its sheer size makes it the largest pool of at-risk revenue on the platform.
- High Activity users are the smallest but most valuable segment (18.5% of users, lowest churn, highest LTV) — losing them is disproportionately costly relative to their low likelihood of churning.

## 📌 Business Recommendations

1. Prioritize win-back campaigns for Low Activity Users

Finding: Low Activity Users make up 41.2% of the base and churn at 39.88% — the largest concentration of preventable churn on the platform.
Recommendation: Launch targeted re-engagement campaigns (win-back emails, personalized recommendations, limited-time incentives) specifically for this segment.

2. Build engagement-nudging programs to move users up a tier

Finding: Moving a user from Low to Moderate Activity represents a potential Lifetime Value uplift of ~$657 per user.
Recommendation: Introduce engagement-building nudges (push notifications, login streaks, personalized content) rather than only reacting to churn after it happens.

3. Protect High Activity Users with a loyalty program

Finding: High Activity Users have the lowest churn (19.65%) and highest LTV ($2,341.77), but are also the smallest segment (18.5%).
Recommendation: Implement a VIP/loyalty program to protect this high-value segment, since retention cost here is likely far lower than the value at risk.

4. Use behavioral data, not demographics, for targeting

Finding: Age, tenure, and country show no meaningful difference across segments.
Recommendation: Build targeting and early-warning systems around behavioral signals (login frequency, session duration, cart abandonment) rather than demographic filters, since demographics do not predict engagement level on this platform.

##🚀 Project Highlights

✔ End-to-end data analytics workflow, from raw data to business recommendation
✔ Tiered missing-value imputation strategy based on missingness severity
✔ Unsupervised clustering validated with both Elbow Method and Silhouette Score, including an explicit statistical-vs-business trade-off discussion
✔ Dollar-quantified business insights tying behavioral segments to churn and revenue
✔ Interactive Power BI dashboard for ongoing segment monitoring
