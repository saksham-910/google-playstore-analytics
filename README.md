# Google Play Store App Analytics 📊

A market analysis notebook exploring ~10,800 Google Play Store app 
listings — category popularity, free vs. paid trends, and estimated 
revenue — built with Pandas and Plotly.

## What it does
- Loads and cleans app listing data (drops unused columns, removes 
  NaN ratings, de-duplicates on `App`+`Type`+`Price`)
- Converts messy string columns (`Installs` with commas, `Price` 
  with `$`) into numeric types
- Engineers a `Revenue_Estimate` feature (`Installs × Price`)
- Visualizes category concentration, genre popularity, free vs. paid 
  installs, and price/revenue by category

## Key Findings
- A handful of categories (Family, Game, Tools) account for a 
  disproportionate share of both app count and installs — the 
  market is heavily concentrated
- Paid apps take a real install hit compared to free apps, but a 
  few categories still generate meaningful estimated revenue 
  despite lower volume
- Genre data needed unpacking first, since many apps list multiple 
  `;`-separated genres in one field before any genre-level analysis 
  was possible

## Tools Used
- Python, Pandas, Plotly Express
- Google Colab (Jupyter Notebook)

## Concepts Covered
- Targeted duplicate handling with `.drop_duplicates(subset=[...])`
- String cleaning + `pd.to_numeric()` conversion
- `.str.split(';', expand=True).stack()` for unpacking multi-value 
  fields
- `.groupby().agg()` and `pd.merge()` for category-level analysis
- Interactive Plotly Express charts (pie, bar, scatter, box) with 
  log-scale axes

Good project — this is exactly the kind of exploratory market 
analysis that shows real data science thinking on your GitHub!
