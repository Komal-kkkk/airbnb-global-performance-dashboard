# airbnb-global-performance-dashboard
Interactive Power BI dashboard analyzing Airbnb's global listings, market share, pricing, reviews, ratings, and host trust.

## 📊 Dashboard Preview

### Overview

![Dashboard Overview](screenshots/overview.png)

### Market Share & Ratings

![Market Share and Ratings](screenshots/market-share-and-ratings.png)

### Reviews & Host Trust

![Reviews and Trust](screenshots/reviews-and-trust.png)

---

## 🎯 Project Objectives

The main objective of this project is to analyze Airbnb's global performance and identify meaningful business insights related to:

- Global listing distribution
- Market share by city
- Property types
- Pricing across room types
- Review frequency
- Customer ratings
- Host verification and profile information
- Monthly review patterns

---

## 🛠️ Tools & Technologies

- **Microsoft Power BI**
- **DAX**
- **Power Query**
- **Data Cleaning & Transformation**
- **Data Visualization**
- **Business Intelligence**

---

## 📌 Dashboard Pages

### 1. Overview

The Overview page provides a high-level summary of Airbnb's global performance.

Key metrics include:

- Total Listings
- Total Cities
- Total Hosts
- Property Types
- Total Reviews

It also includes a trend analysis of new listings over the years and compares different room/property types.

---

### 2. Market Share & Ratings

This page focuses on the geographical distribution and quality of Airbnb listings.

It includes:

- Market share by city
- Superhost vs Non-Superhost listings
- Cumulative market share
- Average price by room type
- City-level rating comparison
- Rating metrics including:
  - Accuracy
  - Cleanliness
  - Communication
  - Location
  - Value

---

### 3. Reviews & Host Trust

This page analyzes customer review behavior and host trust indicators.

It includes:

- Review frequency
- Cumulative percentage of reviewers
- Monthly review distribution
- Host verification status
- Profile picture availability

A host trust analysis was created by combining:

- Host verification status
- Profile picture availability

---

## 📈 Key Insights

### Global Performance

- Airbnb has a large global presence with hundreds of thousands of listings.
- The platform operates across multiple major cities and property types.
- Listing growth increased significantly during the earlier years of the dataset.

### Market Distribution

- Paris, New York, and Sydney represent a significant share of the total listings and views.
- Paris stands out as one of the strongest markets in terms of listings and reviews.
- Hotel rooms have a higher average price compared with other room types.

### Reviews

- A large majority of customers leave only a small number of reviews.
- The cumulative review-frequency analysis shows that frequent reviewers represent a relatively small portion of customers.
- Review activity varies considerably across different months and cities.

### Host Trust

The trust analysis combines host verification and profile-picture availability.

The dashboard shows that:

- **66.9%** of hosts are verified and have a profile picture.
- **32.6%** are not verified but have a profile picture.
- **0.3%** are not verified and do not have a profile picture.
- **0.3%** are verified but do not have a profile picture.

> Note: Percentages depend on the dataset and calculation context used in the dashboard.

---

## 🧮 DAX Measures

Some of the key DAX measures used in this project include:

```DAX
Host Total =
DISTINCTCOUNT(Listings[host_id])

host trust calculation:
Verified_Profile =
CALCULATE(
    [Host Total],
    Listings[host_identity_verified] = "t",
    Listings[host_has_profile_pic] = "t"
)

Percentage calculation:
Verified_Profile% =
DIVIDE(
    [Verified_Profile],
    [Host Total]
)

Similar measures were created for:
- Verified hosts without profile pictures
- Unverified hosts with profile pictures
- Unverified hosts without profile pictures

Business Questions Answered
This dashboard helps answer questions such as:
1. Which cities have the largest Airbnb presence?
2. How has the number of listings changed over time?
3. Which room types have the highest average prices?
4. Which cities have the strongest customer ratings?
5. How frequently do customers leave reviews?
6. How are reviews distributed across different months?
7. What percentage of hosts are verified?
8. How does profile-picture availability relate to host verification?

Dataset
The project uses an Airbnb listings/reviews dataset containing information about:
- Listings
- Hosts
- Cities
- Property types
- Room types
- Prices
- Reviews
- Ratings
- Host verification
- Host profile information
The raw dataset is not included in this repository where redistribution may be restricted.

Dashboard Features
- Interactive Power BI visuals
- KPI cards
- Line and combination charts
- Market share analysis
- Rating analysis
- Review frequency analysis
- Monthly review analysis
- Host trust analysis
- DAX-based calculations
- Interactive filtering
