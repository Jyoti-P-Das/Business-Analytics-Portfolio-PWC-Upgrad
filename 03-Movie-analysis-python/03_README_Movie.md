# 🎬 Movie Dataset Analysis — Python & Exploratory Data Analysis

**Program:** Professional Certificate in Business Analytics & Consulting — upGrad × PwC Academy  
**Domain:** Entertainment & Media Analytics  
**Tools:** Python · Pandas · NumPy · Matplotlib

---

## 🎯 Project Objective

Conduct end-to-end exploratory data analysis on a 100-year movie dataset (1916–2016) using Python to surface meaningful patterns in genre performance, directorial track records, star power, and box office trends. Translate findings into investment and production recommendations for a content studio.

This project demonstrates the full Python analytics workflow: raw data ingestion → cleaning → transformation → multi-level analysis → visualisation → business interpretation. It reflects the kind of data wrangling and analytical thinking expected in data analyst and junior data scientist roles.

---

## 💼 Business Problem

A content production company wanted answers to:
- Which genres generate the highest and most consistent box office returns over decades?
- What is the commercial profile of the most successful directors and actors?
- Which features — budget, genre, language, runtime — correlate most strongly with revenue and audience ratings?
- How has the film industry's composition (languages, genres, budgets) evolved over 100 years?

---

## 📂 Dataset

**Source:** IMDb-derived movie dataset covering 1916–2016 (publicly available educational dataset widely used across Python and EDA training programs)  
**Size:** 5,000+ movies  
**Key Fields:** Title, Genre(s), Director, Lead Actor(s), Release Year, Production Budget, Worldwide Revenue, IMDb Score, Vote Count, Language, Country, Runtime

> Dataset is a publicly available educational resource. Your Jupyter Notebook in `/notebooks` contains all data cleaning steps, analysis, and visualisations with inline explanations.

---

## 🔍 Analysis Performed

### 1. Data Sourcing & Loading
- Loaded with `pandas.read_csv()`, inspected with `.info()`, `.shape`, `.describe()`, `.dtypes`
- Identified structural issues: multi-value genre fields, inconsistent date formats, mixed numeric types

### 2. Data Cleaning
- Handled missing values with targeted imputation and informed row removal
- Converted string-represented numerics (budget, revenue) to float
- Filtered implausible records (e.g. zero-revenue films excluded from ROI analysis)
- Split multi-genre entries into primary genre for category-level analysis
- Final clean dataset ready for analysis

### 3. Univariate Analysis
- Distribution plots (histograms) for budget, revenue, IMDb score, runtime, vote count
- Frequency charts for genre, language, country of origin
- Summary statistics: mean, median, standard deviation, skewness for all numeric fields

### 4. Segmented Univariate Analysis
- Revenue and rating distributions broken down by genre
- Release volume trend by decade — industry growth pattern
- Language-wise average rating comparison

### 5. Bivariate Analysis
- Scatter plots: Budget vs Revenue, Runtime vs Rating, Vote Count vs Revenue
- Box plots: Genre vs Revenue, Genre vs IMDb Score
- Grouped bar charts: Decade-wise genre share over time

### 6. Correlation & Derived Metrics
- Correlation matrix across all numeric features
- **Profitability Ratio** = Revenue / Budget (per film and per genre)
- **Genre ROI** = Average Profitability Ratio by primary genre
- **Director Career Curve** = cumulative revenue trajectory for top 10 directors by total revenue

---

## 📈 Key Findings

- **Action and Adventure** deliver the highest median box office revenue; Animation shows the highest ROI efficiency
- Budget is a weak predictor of success individually — high-budget films show extreme variance in returns
- A Pareto-like pattern holds: the top 5% of directors by film count account for a disproportionate share of total industry revenue
- **IMDb rating and box office revenue are weakly correlated** — critical acclaim does not reliably predict commercial performance
- Non-English films have higher average audience ratings but significantly lower absolute revenues — a globalisation opportunity
- Drama is the highest-volume genre by releases but Action leads in per-film revenue

---

## 💡 Business Recommendations

1. **Invest in Action/Adventure with proven directors** — maximises expected revenue floor and reduces downside risk
2. **Mid-budget Drama and Thriller** projects offer the strongest ROI relative to budget outlay
3. **Prioritise director selection over star casting** — directorial track record predicts success more reliably than individual actors
4. **Explore international co-productions** — non-English market share has been rising since 2005; partnerships offer access with managed risk

---

## 📁 Files in This Folder

```
03-movie-analysis-python/
├── README.md
└── notebooks/
    └── Movie_Assignment_YourName.ipynb ← Full EDA Jupyter Notebook
```

---

## 🎓 Skills Demonstrated

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Data Cleaning` · `Univariate Analysis` · `Segmented Analysis` · `Bivariate Analysis` · `Correlation Analysis` · `Derived Metrics` · `Profitability Analysis` · `EDA` · `Data Visualisation` · `Entertainment Analytics`

---

**Modules:** Introduction to Python + Python for Analytics + Exploratory Data Analysis  

