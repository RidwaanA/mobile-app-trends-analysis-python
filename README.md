# 📱 Mobile Application Download Trends & Category Growth Analysis

# Project Overview
This project analyzes Google Play Store data to uncover trends in app installs, user engagement, and category performance.

Using Python (Pandas, Seaborn, Matplotlib), the analysis identifies high-performing app segments and key drivers of popularity to support data-driven advertising strategies for a marketing agency.

# Business Problem
Zoom Ads aims to optimize ad placements by targeting app categories with the highest user engagement and growth potential.

The challenge:
➡️ Identify which app categories and attributes maximize installs and user interaction.

# Dataset
- ~4,200 mobile applications
- 12 features including:
  App, Category, Rating, Reviews, Installs, Price, Content Rating
- Mix of free and paid apps across 15 categories

# Tools & Technologies
- Python (Pandas, NumPy)
- Data Visualization (Seaborn, Matplotlib)
- Jupyter Notebook

# Data Processing / Methodology
- Cleaned missing values in Rating and Reviews using group-wise median imputation
- Converted data types (e.g., Installs, Reviews → numeric)
- Performed univariate, bivariate, and multivariate analysis
- Engineered features (e.g., size and price bins for deeper insights)
- Conducted correlation and distribution analysis

# Key Code Highlights
### Group-wise median imputation for missing ratings
df['Rating'] = df['Rating'].fillna(
    df.groupby(['Category','Content Rating'])['Rating'].transform('median')
)
