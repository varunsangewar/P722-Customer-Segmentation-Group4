# P722: Customer Segmentation — Business Objective & Hypotheses Foundation
**Group:** Group 4 | **Institute:** ExcelR Hyderabad  
**Author:** Sangewar Varun Rajesh (Business Objective & Hypotheses Lead)  
**Dataset:** marketing_campaign.xlsx (2,240 records, 29 attributes)

---

## 1. Executive Summary & Core Business Problem
Retail marketing campaigns currently treat the entire customer base as a homogeneous audience, resulting in suboptimal marketing ROI, irrelevant promotions, and campaign fatigue. The core objective of this project is to perform unsupervised customer segmentation to identify distinct, actionable customer cohorts based on demographic profiles, purchasing behavior, campaign responsiveness, and channel engagement.

---

## 2. Intended Users & Strategic Decision Scope
* **Target Users:** Marketing Campaign Managers, Product Category Leads, CRM & Retention Teams, and Executive Commercial Stakeholders.
* **Supported Decisions:**
  1. *Promotion Customization:* Differentiating high-margin product offers (e.g., Wines & Meat) from deal-oriented discount promotions.
  2. *Channel Optimization:* Allocating marketing spend effectively across Web, Catalog, and In-Store touchpoints based on cohort preference.
  3. *Retention Intervention:* Targeting churn-risk customers displaying high recency (days since last purchase) with timely re-engagement workflows.

---

## 3. Project Success Criteria
* **Analytical Robustness:** Statistically defensible cluster configurations validated across multiple algorithms (K-Means, Hierarchical, DBSCAN/GMM) using Silhouette Coefficient, Davies-Bouldin Index, and Calinski-Harabasz metrics.
* **Interpretability & Profiling:** Clusters must represent distinct, logically explainable customer behaviors.
* **Reproducibility:** Fully reproducible end-to-end code execution using frozen random seeds and clean data pipelines.
* **Operational Usability:** A functional Streamlit web application capable of classifying single-customer inputs into segments in real time.

---

## 4. Testable Segment Hypotheses (Prior to Clustering)
* **Hypothesis H1 (Affluent Connoisseurs):** Customers with above-median Income and zero children (`Kidhome + Teenhome == 0`) allocate a significantly higher proportion of spend to `MntWines` and `MntMeatProducts` and exhibit lower deal sensitivity (`NumDealsPurchases`).
* **Hypothesis H2 (Budget & Deal Seekers):** Customers with lower-to-middle income and larger family sizes (`Kidhome > 0` or `Teenhome > 0`) have lower average basket sizes but generate a higher ratio of purchases via promotions (`NumDealsPurchases`).
* **Hypothesis H3 (Digital-First Shoppers):** Customers with high web browsing activity (`NumWebVisitsMonth`) and moderate-to-high web purchases (`NumWebPurchases`) represent a distinct digital segment responsive to email promotions (`AcceptedCmp` series).
* **Hypothesis H4 (Lapsed High-Value Cohort):** A measurable sub-group exhibits high cumulative historical spend (`Total_Spend`) but elevated purchase dormancy (`Recency > 60 days`), representing prime targets for win-back campaigns.
* **Hypothesis H5 (Catalog Traditionalists):** High-income, older-generation customers generate a disproportionate volume of `NumCatalogPurchases` and demonstrate higher campaign acceptance rates than the general population.
