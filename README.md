# 📱 Mobile Application Download Trends & Category Growth Analysis

## Project Overview
This project analyzes Google Play Store data to uncover trends in app installs, user engagement, and category performance.

Using Python (Pandas, Seaborn, Matplotlib), the analysis identifies high-performing app segments and key drivers of popularity to support data-driven advertising strategies for a marketing agency.

## Business Problem
Zoom Ads aims to optimize ad placements by targeting app categories with the highest user engagement and growth potential.

The challenge:
➡️ Identify which app categories and attributes maximize installs and user interaction.

## Dataset
- ~4,200 mobile applications
- 12 features including:
  `App`, `Category`, `Rating`, `Reviews`, `Installs`, `Price`, `Content Rating`
- Mix of free and paid apps across 15 categories

## Tools & Technologies
- **Python** (Pandas, NumPy, Seaborn, Matplotlib)
- **Jupyter Notebook**
- **Tableau**

## Data Processing / Methodology
- Cleaned missing values in Rating and Reviews using group-wise median imputation
- Converted data types (e.g., Installs, Reviews → numeric)
- Performed univariate, bivariate, and multivariate analysis
- Engineered features (e.g., size and price bins for deeper insights)
- Conducted correlation and distribution analysis

## Key Code Highlights
```python
// Group-wise median imputation for missing ratings
df['Rating'] = df['Rating'].fillna(
    df.groupby(['Category','Content Rating'])['Rating'].transform('median')
)
```
```python
// Top categories by reviews
df.groupby(['Category'])['Reviews'].mean().reset_index().sort_values('Reviews', ascending=False)
```
```python
// Correlation analysis
plt.figure(figsize=(11,6))
sns.heatmap(df.corr(), annot=True, vmin=-1, vmax=1, fmt='.2f', cmap='Spectral');
```
```python
// Engagement relationship
sns.lmplot(data=df, x='Installs', y='Reviews', ci=None)
```

## Visualization / Dashboard
**Python (Jupyter Notebook)**
- 📌 Distribution plots for installs, reviews, and ratings
- 📌 Category-level performance comparisons
- 📌 Correlation heatmaps and regression plots
- 📌 Multivariate trend analysis (installs by category, pricing, and app size)

**Tableau**
- 📌 Stacked bar charts: Apps split by paid/free status across categories and content ratings — broken down further by ad support, in-app purchases, and editor's choice status
- 📌 Bar chart: Average installs across app categories
- 📌 Bar chart: Average installs across content ratings
- 📌 Pareto chart: Category installs — showing which categories drive the majority of total installs
- 📌 Pareto chart: Content rating installs — showing which content ratings account for the bulk of install volume
- 🔗 **[View Live Dashboard on Tableau Public](https://public.tableau.com/views/MobileApplicationDownloadTrendsCategoryGrowthAnalysis/AppsOverviewInstallationSummary?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

## Key Insights
- Top-performing categories:
  → Game, Photography, Sports (with Communication and Others close behind)
- Highest engagement segments:
  → Teen and Everyone 10+ content ratings
- Strong correlation:
  → Reviews and Installs (high engagement drives visibility and growth)
- Market structure:
  → 92% of apps are free; paid apps represent a small but niche opportunity
- Monetization signals:
  → Apps with ads, in-app purchases, or editor’s choice status perform better
- Low-performing categories:
  → Medical, Finance, Lifestyle, Business, Books & Reference

## Recommendations
- Prioritize ad placements in:
  → Game, Photography, Sports, Communication categories
- Target audiences:
  → Teen and Everyone 10+ segments
- Focus on apps that:
  - → Support ads
  - → Include in-app purchases
  - → Have strong review volumes
- Pricing strategy insights:
  - → Free apps dominate
  - → Paid apps under $20 perform best in select categories

## Outcome / Impact
This analysis enables:
- ✅ Smarter ad targeting decisions
- ✅ Improved ROI on campaign spend
- ✅ Identification of high-growth app segments
- ✅ Data-driven prioritization of advertising investments

## Next Steps
- Build a predictive model for app installs
- Integrate time-series trend analysis
- Develop an interactive Tableau dashboard for stakeholders
