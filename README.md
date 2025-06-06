# Quantium Analytics: Chip Purchase Behavior Analysis

## Project Overview

This project analyzes customer purchasing behavior for chip products to provide strategic recommendations for category management. The analysis focuses on understanding customer segments and their purchasing patterns to inform commercial strategy.

<div align="center">
  <img src="img/quantium-logo.jpg" alt="Quantium Logo" width="900"/>
</div>

## Business Context

**Client**: Julia (Category Manager)  
**Objective**: Analyze chip purchasing trends and behaviors across customer segments to support upcoming category review  
**Key Focus**: Customer segmentation and purchasing behavior metrics with commercial applications

## Dataset Description

### Transaction Data (`QVI_transaction_data.xlsx`)
- **Records**: 246,740 transactions (after data cleaning)
- **Time Period**: July 1, 2018 - June 30, 2019
- **Key Fields**:
  - `DATE`: Transaction date
  - `STORE_NBR`: Store identifier
  - `LYLTY_CARD_NBR`: Customer loyalty card number
  - `PROD_NAME`: Product name
  - `PROD_QTY`: Quantity purchased
  - `TOT_SALES`: Total sales amount

### Customer Data (`QVI_purchase_behaviour.csv`)
- **Records**: 72,637 unique customers
- **Key Fields**:
  - `LYLTY_CARD_NBR`: Customer loyalty card number
  - `LIFESTAGE`: Customer life stage (7 categories)
  - `PREMIUM_CUSTOMER`: Customer price sensitivity (Budget/Mainstream/Premium)

## Data Quality & Cleaning

### Issues Identified & Resolved
1. **Outlier Removal**: Removed customer 226000 with unusually high purchase quantities (200 packets)
2. **Product Filtering**: Excluded salsa products to focus on chip analysis
3. **Date Conversion**: Converted Excel date format to proper datetime
4. **Brand Standardization**: Standardized brand names (e.g., "RED" → "RRD")

### Final Dataset Statistics
- **Transactions**: 246,740
- **Unique Products**: 114
- **Unique Customers**: 72,637
- **Date Range**: 365 days
- **Pack Sizes**: 70g - 380g

## Key Features Engineered

### Derived Variables
- **`PACK_SIZE`**: Extracted package size in grams from product names
- **`BRAND`**: Extracted brand name from product names
- **`PRICE_PER_UNIT`**: Calculated price per unit (TOT_SALES / PROD_QTY)

### Customer Segments
- **Life Stages**: Young Singles/Couples, Midage Singles/Couples, Young Families, Older Families, Retirees, New Families, Older Singles/Couples
- **Premium Categories**: Budget, Mainstream, Premium

## Analysis Framework

### 1. Exploratory Data Analysis
- **Temporal Patterns**: Transaction volume over time
- **Product Distribution**: Pack sizes and brand popularity
- **Customer Behavior**: Purchase quantities and frequencies

### 2. Customer Segment Analysis
Four key metrics analyzed across segments:
- **Total Sales**: Revenue generation by segment
- **Customer Count**: Size of each segment
- **Average Units per Customer**: Purchase intensity
- **Average Price per Unit**: Price sensitivity indicators

### 3. Statistical Testing
- T-test comparing mainstream vs. other customer price sensitivity
- **Result**: Statistically significant difference (p < 0.05, t = 37.83)

### 4. Deep Dive: Target Segment Analysis
Focus on **Mainstream Young Singles/Couples** segment:
- **Brand Affinity Analysis**: Preference indices for different brands
- **Pack Size Preferences**: Size preference patterns
- **Commercial Insights**: Actionable recommendations

## Key Findings

### Customer Segment Insights
1. **Highest Revenue Generators**: 
   - Older Families (Mainstream): $124,648
   - Young Singles/Couples (Mainstream): $147,582

2. **Price Sensitivity**:
   - Young Singles/Couples pay premium prices ($4.07/unit for Mainstream)
   - Significant difference between mainstream and other segments

3. **Purchase Behavior**:
   - Older Families have highest purchase intensity (9.3 units/customer)
   - Young segments show consistent purchasing patterns

### Brand & Product Preferences
**Top Brands by Affinity (Mainstream Young Singles/Couples)**:
1. Tyrrells (1.21x population average)
2. Twisties (1.20x)
3. Doritos (1.19x)
4. Kettle (1.18x)

**Preferred Pack Sizes**:
1. 270g (1.25x affinity)
2. 380g (1.23x affinity)
3. 330g (1.20x affinity)

## Strategic Recommendations

### 1. Target Segment Focus
- **Primary Target**: Mainstream Young Singles/Couples
- **Rationale**: High revenue generation, premium price tolerance, distinct preferences

### 2. Product Strategy
- **Brand Portfolio**: Strengthen premium offerings (Tyrrells, Kettle)
- **Pack Size Optimization**: Focus on larger pack sizes (270g, 330g, 380g)
- **Premium Positioning**: Leverage willingness to pay higher prices

### 3. Commercial Applications
- **Category Planning**: Allocate shelf space based on segment preferences
- **Pricing Strategy**: Maintain premium pricing for target segments
- **Promotional Focus**: Target high-affinity brands to key segments

## Technical Implementation

### Tools & Libraries Used
```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy import stats
```

### Analysis Workflow
1. **Data Loading & Validation**
2. **Exploratory Data Analysis**
3. **Feature Engineering**
4. **Customer Segmentation**
5. **Statistical Testing**
6. **Insight Generation**
7. **Visualization & Reporting**

## Files Structure
```
├── LICENSE
│
├── README.md                     # The top-level README for developers using this project
│
├── data/
│   ├── processed/                # The final, canonical data sets for modeling
│   └── raw/                      # The original, immutable data dump
│       ├── QVI_transaction_data.xlsx    # Transaction data
│       └── QVI_purchase_behaviour.csv   # Customer data
│
├── notebooks/                    # Jupyter notebooks for EDA
│   └── feature_analysis.ipynb    # Main EDA analysis notebook
│ 
│
├── figures/                      # Generated graphics and figures to be used in reporting
│
├── img/                          # Project related files
│
└── requirements.txt              # The requirements file for reproducing the analysis environment
```


## Usage Instructions

1. **Data Preparation**: Load both transaction and customer datasets
2. **Run Cleaning**: Execute data quality and cleaning procedures
3. **Feature Engineering**: Create derived variables (pack size, brand, price per unit)
4. **Analysis**: Run customer segmentation and affinity analysis
5. **Visualization**: Generate charts for business presentation

## Business Impact

This analysis provides Julia with:
- **Data-driven insights** for category review
- **Specific recommendations** for product portfolio
- **Customer segment strategies** for revenue optimization
- **Statistical validation** of findings for confident decision-making

## Next Steps

1. **Deeper Segmentation**: Further analyze sub-segments within target groups
2. **Seasonality Analysis**: Investigate seasonal purchasing patterns
3. **Store-level Analysis**: Understand geographic/store-specific trends
4. **Competitive Analysis**: Compare against industry benchmarks

---

*Analysis completed as part of Quantium Analytics virtual experience program*
