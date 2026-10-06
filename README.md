# Nigeria Sales Dataset - Data Cleaning & Transformation Project 🇳🇬

A comprehensive data cleaning and preprocessing project using Python (Pandas, NumPy) and Jupyter Notebooks. This project demonstrates real-world data quality issues and practical solutions for transforming messy data into a clean, analysis-ready dataset.

##  Project Overview

This portfolio project tackles a common data science challenge: **cleaning and transforming a messy Nigeria sales dataset**. The dataset contains 550 sales records with multiple data quality issues including missing values, inconsistent formatting, and calculation errors. Through systematic exploration and transformation, I've documented every step using Git and GitHub to showcase my data cleaning methodology.

### Dataset Summary
- **Original Records:** 550 sales transactions
- **Original Columns:** 9 (Customer Name, State, Product, Units Sold, Unit Price, Total Sale, Sale Date, Sales Channel, Order ID)
- **Final Columns:** 8 (Order ID dropped due to high missing rate)
- **Date Range:** July 2023 - July 2025

##  Data Quality Issues Identified & Fixed

### 1. **Missing Values**
| Column | Missing Count | Strategy |
|--------|---------------|----------|
| Customer Name | 43 | Filled with mode (most frequent value) |
| Units Sold | 395 | Filled with median (robust to outliers) |
| Unit Price | 55 | Filled with median |
| Total Sale | 413 | Recalculated from Units Sold × Unit Price |
| Sales Channel | 106 | Filled with mode (Direct) |
| Order ID | 40 | Column dropped (high missing rate & low relevance) |

### 2. **Inconsistent Categorical Values**
- **Products:** Mixed case variations (e.g., "KEYBOARD", "Keyboard") → Standardized to title case
- **States:** Mixed case variations (e.g., "lagos", "Lagos", "rivers") → Standardized for consistency
- **Result:** 16 unique product types consolidated into consistent format

### 3. **Data Calculation Issues**
- **Total Sale Validation:** Identified discrepancy between actual and calculated values (difference: ₦2,185.54 avg)
- **Solution:** Recalculated all Total Sale values as: `Units Sold × Unit Price` for consistency

### 4. **Data Type Corrections**
- Sale Date properly converted to datetime format
- Numerical columns validated as float64
- Categorical columns maintained as object type

##  Key Statistics (Cleaned Dataset)

```
Dataset Dimensions: 550 rows × 8 columns

Units Sold:
  - Mean: 46.86 units
  - Range: 1 - 100 units
  - Median: 47 units

Unit Price:
  - Mean: ₦155,703.70
  - Range: ₦1,403.13 - ₦299,437.80

Total Sale:
  - Mean: ₦7,075,166
  - Range: ₦57,887.04 - ₦28,734,590
```

##  Project Structure

```
excel-data-cleaning-Nigeria-sales/
├── README.md                              # Project documentation
├── Cleaning tips.txt                      # Cleaning notes & insights
├── data/
│   ├── nigeria_messy_sales_dataset.xlsx   # Original Excel file
│   ├── nigeria_messy_sales_dataset.csv    # Original CSV export
│   ├── DATA_CLEANING.ipynb                # Main Jupyter notebook with all transformations
│   └── cleaned_dataset.csv                # Final cleaned & processed dataset
└── .gitignore                             # Git ignore rules
```

##  Technologies & Tools Used

- **Python 3.x** - Primary programming language
- **Pandas** - Data manipulation & transformation
- **NumPy** - Numerical computations
- **Matplotlib & Seaborn** - Data visualization
- **Jupyter Notebook** - Interactive analysis & documentation
- **Git & GitHub** - Version control & collaboration
- **Microsoft Excel** - Initial data inspection

##  Cleaning Methodology

The project follows a systematic data cleaning pipeline:

1. **Data Loading & Exploration**
   - Loaded Excel file into Pandas DataFrame
   - Inspected shape, data types, and basic statistics
   - Identified missing values and duplicates

2. **Missing Value Analysis**
   - Calculated missing count per column
   - Analyzed distribution before imputation
   - Selected appropriate imputation strategies:
     - **Mode** for categorical (Customer Name, Sales Channel)
     - **Median** for numerical (Units Sold, Unit Price)
     - **Calculation** for derived fields (Total Sale)

3. **Data Standardization**
   - Normalized product names (case conversion)
   - Standardized state names for consistency
   - Verified date format integrity

4. **Data Validation**
   - Confirmed calculated vs. actual Total Sales alignment
   - Removed irrelevant columns with high missing rates (Order ID)
   - Generated summary statistics to verify transformations

5. **Data Export**
   - Saved cleaned dataset to CSV format
   - Ready for analysis and modeling

##  Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Running the Notebook
```bash
jupyter notebook data/DATA_CLEANING.ipynb
```

### Using the Cleaned Data
```python
import pandas as pd

# Load cleaned dataset
df = pd.read_csv('data/cleaned_dataset.csv')

# Verify structure
print(df.info())
print(df.describe())
```

##  Next Steps & Future Enhancements

This project is **actively under development**. Planned improvements include:

- [ ] **Exploratory Data Analysis (EDA)**
  - Statistical summaries and distributions
  - Correlation analysis between sales metrics
  - Time series trends analysis

- [ ] **Advanced Visualizations**
  - Sales by state (geographical heatmaps)
  - Product performance comparisons
  - Sales channel effectiveness analysis
  - Seasonal trends and patterns

- [ ] **Data Quality Reporting**
  - Automated data quality checks
  - Detailed imputation impact assessment
  - Before/after quality metrics dashboard

- [ ] **Documentation Improvements**
  - Interactive HTML report generation
  - Data dictionary with metadata
  - Cleaning validation statistics

- [ ] **Feature Engineering**
  - Customer segmentation analysis
  - Sales performance scoring
  - Regional profitability analysis

##  Key Learnings & Skills Demonstrated

✅ **Data Cleaning & Validation** - Identified and resolved data quality issues  
✅ **Missing Data Handling** - Applied statistical methods for imputation  
✅ **Data Standardization** - Ensured consistency across categorical variables  
✅ **Python & Pandas Proficiency** - Leveraged powerful data manipulation tools  
✅ **Problem-Solving** - Made data-driven decisions on imputation strategies  
✅ **Version Control** - Documented every step with meaningful Git commits  
✅ **Documentation** - Comprehensive project documentation for reproducibility  

##  Data Quality Improvements Summary

| Metric | Before | After |
|--------|--------|-------|
| **Complete Records** | ~13% | 100% |
| **Missing Values** | 1,045 | 0 |
| **Consistent Formatting** | ❌ | ✅ |
| **Valid Calculations** | ~25% | 100% |
| **Ready for Analysis** | ❌ | ✅ |

##  Author

**Conrad Nats** - Data Science & Analytics Student (Year 2)

##  Connect With Me

- **GitHub:** [@ConradNats](https://github.com/ConradNats)
- **Portfolio Project:** Cleaning and transforming real-world data for practical experience

##  License

This project is open source and available for educational and portfolio purposes.

---

**Last Updated:** October 4, 2026  
**Status:** 🟡 In Active Development  
**Latest Changes:** Data cleaning pipeline completed, EDA visualizations in progress

