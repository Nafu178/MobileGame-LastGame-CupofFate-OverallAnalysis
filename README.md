# Last Game - Cup of Fate | Google Play Console Data Analysis

A data analysis project on a published indie mobile game using real exported data from Google Play Console. This project covers the full analyst workflow — from raw CSV files to cleaned data, visualizations, and actionable insights for the developer.

---

## Background

My friend is an indie game developer who has published multiple games on the Google Play Store. For his game **"Last Game - Cup of Fate"**, he wanted to better understand how the game was performing — what was working, what wasn't, and what he should do next.

He exported the data manually from Google Play Console and I performed the full analysis.

---

## Dataset

Data was exported directly from Google Play Console covering **November 2025 to May 2026**.

| Section | Description | Files |
|---------|-------------|-------|
| Installs | Daily device installs, uninstalls, active devices | 7 monthly CSVs |
| Ratings | Daily and total average ratings | 6 monthly CSVs |
| Crashes | Daily crashes and ANRs | 2 monthly CSVs |
| Store Performance | Store visitors, acquisitions, conversion rate by country | 7 monthly CSVs |

> Note: Raw data files are not included in this repository as they contain private developer statistics.

---

## Tools & Libraries

- **Python 3** via Google Colab
- **Pandas** — data loading, cleaning, merging
- **Matplotlib** — all visualizations
- **Seaborn** — chart styling

---

## Project Structure

```
LastGame_Analysis/
├── LastGame_Analysis.ipynb   ← Main analysis notebook
├── README.md
└── outputs/
    ├── installs_analysis.png
    ├── crashes_analysis.png
    ├── ratings_analysis.png
    ├── store_analysis.png
    ├── country_analysis.png
    ├── complete_overview.png
    └── summary_report.png
```

---

## Analysis Workflow

### 1. Data Loading & Cleaning
- Loaded multiple monthly CSV files per section using `pd.concat()`
- Handled UTF-16 encoding from Google Play Console exports
- Converted all Date columns from `object` to `datetime64`
- Sorted all dataframes chronologically

### 2. Exploratory Data Analysis (EDA)
- Inspected data types and structure for each dataset
- Ran `.describe()` to understand distributions and spot anomalies
- Identified missing dates (zero-crash days not recorded by Google)

### 3. Visualization
- Install trends with phase annotations
- Crash overlay against install spike
- Rating trajectory with danger zone threshold
- Store conversion rate vs industry average
- Country-level breakdown of visitors and acquisitions
- Complete 4-in-1 overview timeline

### 4. Insights & Recommendations
- Identified a viral spike event on March 2, 2026
- Traced the cause-and-effect chain across all four datasets
- Identified core audience geography
- Produced prioritized recommendations for the developer

---

## Key Findings

**01 — Viral Spike on March 2, 2026**
Daily installs jumped from near zero to 591 in 2 days. Store conversion rate hit 20%+, confirming visitors came with strong intent — consistent with a content creator post in Latin America.

**02 — Crashes Peaked During the Viral Window**
Daily crashes peaked at 10 on March 5–7, exactly when installs were highest. New players encountered bugs on their very first session, triggering mass uninstalls of 350 per day within 48 hours.

**03 — Rating Collapsed from 5.0 to 2.7 in One Week**
Before the spike the game held a clean 5-star rating. The viral audience gave predominantly 1 and 2 star ratings after experiencing crashes. The total average dropped from 5.0 to 3.1 within 7 days and continued declining to 2.7 by April.

**04 — Rating is Now Blocking Future Growth**
April saw a second traffic wave with 4,000+ daily store visitors but near-zero conversions. People are finding the game — the 2.7 star rating is actively discouraging installs.

**05 — Core Audience is Latin America**
Mexico (20,435 visitors, 1,104 installs) and Brazil (16,468 visitors, 758 installs) dominate all metrics. Colombia, Chile, and Peru also show strong presence.

---

## Recommendations

| Priority | Action |
|----------|--------|
| URGENT | Fix the crashes before any promotion or marketing |
| HIGH | Actively recover the rating — ask existing happy players to leave a review |
| HIGH | Find who caused the March viral spike and reach out to them |
| MEDIUM | Localize the store listing into Spanish and Portuguese |

---

## Charts

### Complete Game Health Overview
![Complete Overview](outputs/complete_overview.png)

### Install Analysis
![Installs](outputs/installs_analysis.png)

### Crash Analysis
![Crashes](outputs/crashes_analysis.png)

### Ratings Analysis
![Ratings](outputs/ratings_analysis.png)

### Store Performance
![Store](outputs/store_analysis.png)

### Top Countries
![Countries](outputs/country_analysis.png)

### Summary Report
![Summary](outputs/summary_report.png)

---

## What I Learned

- How to work with real exported data from Google Play Console including encoding issues (UTF-16)
- Combining multiple monthly CSV files into a single dataframe
- How to read and interpret mobile game KPIs (ANRs, active device installs, store conversion rate)
- Cross-dataset analysis — connecting patterns across installs, crashes, ratings, and store performance
- How a single viral moment can have cascading positive and negative effects on a game's long-term health

---

## About

**Analyst:** Naf
**Developer / Data Owner:** MechaZero Game
**Game:** Last Game - Cup of Fate ([Google Play Store](https://play.google.com/store/apps/details?id=com.mechazerogame.lastgame))
**Analysis Period:** November 2025 – May 2026
