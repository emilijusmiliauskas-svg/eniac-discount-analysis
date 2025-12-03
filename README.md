# ENIAC – Discount Strategy and Revenue Performance Evaluation

## Overview
This project analyzes ENIAC’s discount strategies and their impact on revenue performance.  
The goal is to determine whether deeper discounts lead to higher overall revenue and how discounting behavior varies by product category, brand, and time.

The project is designed as a storytelling-through-analytics exercise, demonstrating data preparation, transformation, visualization, and business-oriented interpretation.

---

## Objectives
- Understand discounting patterns across categories and products.
- Evaluate revenue uplift relative to discount depth.
- Identify products with overspending on discounts (margin leakage).
- Provide guidance for discount strategy optimization.

---

## Repository Structure
```
eniac-discount-analysis/
│
├── notebooks/
│   └── eniac_analysis.ipynb
│
├── slides/
│   └── Eniacs-discount-strategy-and-revenue-performance-evaluation.pdf
│
├── data/
│   ├── raw-data/         (Not included in repo due to size)
│   └── clean-data/       (Not included in repo due to size)
│
└── README.md
```

---

## Data Availability
Raw and cleaned datasets were not uploaded to GitHub because:
- Size limitations (GitHub file size limits)
- Contains sample business-like transactional data

To run the notebook, create:

```
/data/raw-data/
/data/clean-data/
```

Then place the CSV files in the appropriate folder paths.

---

## Key Transformations Performed
- Removed duplicate entries — enforced SKU-level uniqueness.
- Standardized product names and category hierarchy.
- Corrected corrupted price formats (extra decimals, incorrect separators).
- Imputed missing values or selectively removed rows where needed.
- Converted timestamp strings into `datetime64` for time-based analysis.
- Validated referential integrity:
  - `orders ↔ orderlines`
- Ensured alignment of pricing fields:
  - `products.price`, `orderlines.unit_price`, `orders.total_paid`
- Outlier removal using IQR (box-plot statistical filtering).
- Converted price fields to numeric to enable aggregation.
- Verified consistency in categorical labels.

---

## Categorization Strategy
Because product categories were inconsistent:

- `regex` + `.str.*()` pandas functions used for pattern extraction
- Brand extracted from SKU and merged with product naming
- Several iterative classification passes required
- Final categories optimized for reporting **clarity**, not taxonomic accuracy

Context and business storytelling shaped classification decisions.

---

## Analytical Focus
Primary question:
> **Do deeper discounts correlate with higher revenue?**

Analysis included:
- Revenue vs. discount severity
- Category-specific discount responsiveness
- Seasonal / promotional time-based trends

These findings are summarized visually in the slides.

---

## Tools Used
- Google Colab
- Python (Pandas, Seaborn)
- Regex for rule-based classification
- IQR outlier detection
- Presentation built using Gamma

---

## Limitations
- Dataset size limits predictive modeling reliability
- Missing factors: competition, market trends, inflation, seasonality
- Findings are **directional**, not **causation proof**
- Discount impact depends on external factors not captured here

---

## Slides
The presentation summarizing business insights is located in:

```
/slides/Eniacs-discount-strategy-and-revenue-performance-evaluation.pdf
```

---

## About This Project
This project was created as a portfolio case study to demonstrate capability in:
- Data cleaning and transformation
- Exploratory data analysis
- Business-driven analytics storytelling
- Communication of insights through slides

It reflects real-world-style issues: unclean data, incomplete categories, and decision-making with uncertainty.

---

