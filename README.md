# 🛍️ Customer Behavior Analysis using Python & Power BI

## 📌 Project Overview
This project analyzes customer behavior using Python and Power BI to understand user engagement, identify customer segments, analyze churn patterns, and provide business recommendations.
The analysis combines exploratory data analysis (EDA), customer segmentation using K-Means Clustering, and an interactive Power BI dashboard to help businesses make data-driven decisions for customer retention and engagement.

## 🎯 Business Problem
Understanding customer behavior is essential for improving customer retention and maximizing business value.
This project aims to answer several business questions:
- Which customers are the most valuable?
- Which customer segment has the highest risk of churn?
- Does user activity influence purchasing behavior?
- Which customer segment should become the company's priority?

## 🎯 Project Objectives
- Explore customer behavior using exploratory data analysis.
- Identify relationships between key behavioral metrics.
- Segment customers based on behavioral characteristics using K-Means Clustering.
- Profile each customer segment using business metrics such as Lifetime Value, Cart Abandonment Rate, and Churn Rate.
- Visualize customer behavior through an interactive Power BI dashboard.
- Generate actionable business insights to support customer engagement strategies.

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

## 🛠 Tools & Libraries
### Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

### Business Intelligence
- Microsoft Power BI

## 📈 Project Workflow

```text
Business Understanding
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis (EDA)
        ↓
Correlation Analysis
        ↓
Customer Segmentation (K-Means)
        ↓
User Behavior Analysis
        ↓
Power BI Dashboard
        ↓
Business Insights
        ↓
Business Recommendations
```

## 📊 Exploratory Data Analysis

The exploratory analysis focused on:

- Dataset overview
- Data cleaning and preprocessing
- Summary statistics
- Correlation analysis among key behavioral variables

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

<img width="4775" height="4464" alt="user behavior_page-0001" src="https://github.com/user-attachments/assets/b67105c6-b142-4200-afe5-cc5c65702006" />

## 💡 Key Insights
### 1. High Activity Users generate the highest business value.
- Highest Login Frequency
- Highest Total Purchases
- Highest Lifetime Value
- Lowest Cart Abandonment

### 2. Low Activity Users have the highest churn risk.
- Highest Churn Rate
- Highest Cart Abandonment Rate
- Lowest Lifetime Value

### 3. Customer engagement positively influences purchasing behavior.
Users with higher Login Frequency and longer Session Duration tend to generate higher Total Purchases and Lifetime Value.

### 4. Customer segmentation successfully distinguishes different user behaviors.
Behavioral metrics clearly separate customers into meaningful segments, enabling targeted marketing strategies.

## 📌 Business Recommendations

### Low Activity Users

- Personalized email campaigns
- Push notifications
- Discount campaigns
- Retargeting promotions

---

### Moderately Active Users

- Loyalty rewards
- Product recommendations
- Personalized offers

---

### High Activity Users

- VIP Membership
- Referral Program
- Exclusive promotions
- Early access campaigns

---
