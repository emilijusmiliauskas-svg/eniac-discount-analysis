# Eniac Discount Impact Analysis  
Exploring whether offering price discounts increases revenue and benefits the business.

---

## Project Overview  
This project analyzes historical sales data to assess if discounting strategies improve financial outcomes.  
The goal was **descriptive and prescriptive analysis**.  
While some business questions requested predictive insights, the dataset did **not provide enough historical depth or column completeness** to build reliable predictive models.

---

## Dataset and Source
Tables analyzed:
- **products**
- **orders**
- **orderlines**

The dataset contained significant structural and quality issues requiring extensive cleaning before valid analysis.

---

## Data Cleaning Process
Key transformations performed:

- Removed duplicate entries (SKU-level uniqueness ensured).
- Standardized product names and category hierarchy.
- Identified and resolved corrupted price formats (two decimal markers, extra precision).
- Handled missing values via imputation or selective removal.
- Converted string timestamps into proper `datetime64` format to enable time–based analysis.
- Ensured orders existed in both `orders` and `orderlines`.
- Validated pricing integrity across:
  - `products.price`
  - `orderlines.unit_price`
  - `orders.total_paid`
- **Outlier removal using IQR box–plot methodology** where extreme values artificially biased averages.
- Converted price fields to numeric to enable aggregation and statistical exploration.

---

## Categorization Strategy
Because product categories were inconsistent:

- Regex + pandas `.str` methods used to derive categories.
- Brand extracted from SKU and combined with product name to refine classification.
- Multiple iterative passes were required — **storytelling and context** were essential to decision making.
- Final categories were optimized for reporting clarity, not perfection.

---

## Analytical Focus  
The core question:  
**Do deeper discounts correlate with higher revenue?**

Evaluation included:
- Revenue vs. discount severity
- Category-specific discount sensitivity
- Time–based analysis (seasonality & promotions)

Findings are summarized visually in the project slides.

---

## Tools Used
- Google Colab
- Python
- Pandas
- Seaborn (visualization)
- IQR outlier detection
- Regex rule–based classification
- Gamma — presentation slides

---

## Limitations
- Dataset size limited predictive modeling.
- Discount effects may depend on external factors not included (competition, inflation, seasonality).
- Analysis is directional, not causal.

---

## Repository Structure

