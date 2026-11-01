# Slide 1: Title & Team Overview
- Project: P722 – Customer Segmentation (ExcelR Hyderabad)
- Group: Group 4 (7 Members)
- Week 1 Focus: Business Objective, Kick-off & Exploratory Data Analysis (EDA)
- Presenter: Janjarapu Varstihkar (Week 1 Review Presenter) / Content Lead: Sangewar Varun Rajesh

# Slide 2: Core Business Problem & Decision Scope
- Problem: Mass, unsegmented marketing produces diminishing ROI, high unsubscribe rates, and untargeted discount spend.
- Solution: Algorithmic customer clustering across demographic, spend, channel, and promotion dimensions.
- Target Stakeholders: Campaign Strategists, Category Managers, CRM Teams.

# Slide 3: Dataset Snapshot & Baseline Characteristics
- Raw Records: 2,240 customer profiles, 29 attributes
- Observation Window: July 30, 2012 – June 29, 2014
- Feature Pillars:
  * Demographics: Year_Birth, Education, Marital_Status, Income, Kidhome, Teenhome
  * Products (6): Wines, Fruits, Meat, Fish, Sweets, Gold
  * Channels (4): Web, Catalog, Store, Web Visits
  * Promotions (6): AcceptedCmp1–5, Response, NumDealsPurchases

# Slide 4: Data Quality & Boundary Risks (Handoff from Data Quality Lead)
- Missing Data: 24 missing values in `Income` (1.07%) — Requires median/KNN imputation strategy.
- Repetitive Records: 182 rows repeat across non-ID fields; investigation underway to distinguish genuine twins from duplicate logs.
- Category Anomalies: Sparse `Marital_Status` categories ("Absurd", "YOLO", "Alone") requiring standardized mapping.
- Uninformative Attributes: `Z_CostContact` and `Z_Revenue` are constant across all 2,240 records — Dropped from clustering.
- Outlier Range: `Year_Birth` min = 1893 (age > 120); `Income` max = 666,666.

# Slide 5: EDA Workstream Progress (Handoffs from Analysts)
- Demographics (John Williams I): Income distribution skewness; family size segmentation.
- Spending Behaviour (Daniel Abhishek): Wine and Meat dominate total wallet share; top 20% spanders drive over 60% of total revenue.
- Channels & Campaigns (Manasi Sarnobat): In-Store purchases remain highest volume; overall campaign response rates remain low (<15%).
- Relationships (Yatham Paramesh): Strong correlation between Income and Total Spend; weak correlation between Deals and Income.

# Slide 6: Testable Segment Hypotheses
- H1: Affluent Connoisseurs (High Income, 0 Kids, High Wine/Meat spend, Low deals).
- H2: Deal & Budget Maximizers (Lower Income, Kids present, High NumDealsPurchases).
- H3: Digital-First Engagers (High Web Visits & Web Purchases, responsive to email campaigns).
- H4: Lapsed High-Value Cohort (High cumulative historical spend, Recency > 60 days).
- H5: Catalog Traditionalists (High Income, older demographic, high catalog purchase share).

# Slide 7: Week 2 Commitments & Roadmap
- Feature Engineering: Total_Spend, Customer_Tenure, Total_Purchases, Children count.
- Preprocessing: Scaling, outlier clipping, and dimensionality reduction assessment (PCA).
- Model Suite Execution: K-Means, Hierarchical Agglomerative, DBSCAN/GMM.
- Evaluation Gate: Silhouette Analysis, Elbow method, and cluster stability checks.