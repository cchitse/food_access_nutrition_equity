# Food Access and Nutrition Equity Data Wrangling Project

This project investigates food accessibility, nutritional quality, and socioeconomic disparities across counties in the state of Texas. It demonstrates robust data wrangling techniques by implementing a complete data pipeline across four technical platforms: 

- **Python (pandas)**
- **R (tidyverse)**
- **SQL**
- **Excel(PowerQuery)**.

The primary objective is to construct a reproducible data wrangling workflow that transforms messy, real-world datasets into clean, analysis-ready outputs suitable for investigating food access inequities.


<div align="center">

![MIT License](https://img.shields.io/badge/license-MIT-yellow.svg)
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB.svg?logo=python&logoColor=white)](https://www.python.org/downloads/release/python-380/)
![SQL](https://img.shields.io/badge/SQL-Database-CC2927.svg?logo=microsoftsqlserver&logoColor=white)
![R](https://img.shields.io/badge/R-4.0+-276DC3.svg?logo=r&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-2016+-217346.svg?logo=microsoftexcel&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-10+-0078D6.svg?logo=windows&logoColor=white)

</div>

## ✨ Research Questions

1. **Urban vs Rural Disparities**: How does food access differ between urban and rural counties in Texas?
2. **Poverty-Access Correlation**: What is the relationship between poverty rates and limited food access?
3. **Demographic Disparities**: Which demographic groups face the greatest challenges in accessing healthy food?
4. **Education-Access Relationship**: How does educational attainment correlate with food accessibility?
5. **Nutritional Profiles**: What are the nutritional characteristics of different food categories?

## 🎯 Data Sources

### 1. USDA Food Access Research Atlas
- **Source**: United States Department of Agriculture
- **File**: `FoodAccessResearchAtlasData.csv`
- **Dimensions**: 72,531 rows × 147 columns
- **Description**: Census-tract-level indicators of supermarket accessibility and food access challenges for different demographic groups
- **Key Variables**: Population, income, race, SNAP benefits, geographic accessibility measures

### 2. U.S. Census County Demographics
- **Source**: U.S. Census Bureau via CORGIS
- **File**: `county_demographics.csv`
- **Dimensions**: 3,139 rows × 43 columns
- **Description**: County-level demographic and socioeconomic data from 2010-2019
- **Key Variables**: Age distribution, education, employment, ethnicity, household income, housing

### 3. CORGIS Food Nutrition Database
- **Source**: USDA Food Composition Database via CORGIS
- **File**: `food.csv`
- **Dimensions**: 7,083 rows × 38 columns
- **Description**: Nutritional breakdowns of thousands of food items
- **Key Variables**: Macronutrients, vitamins, minerals, food categories

## 📱 Project Structure

```
Food_Access_Nutrition_Equity/
│
├── data/
│   ├── raw/                    # Original data files
│   │   ├── FoodAccessResearchAtlasData.csv
│   │   ├── county_demographics.csv
│   │   └── food.csv
│   └── processed/               # Cleaned and merged datasets
│       ├── Texas_County_Merged.csv
│       ├── Texas_Tract_FoodAccess.csv
│       └── Food_Nutrition_Clean.csv
│
├── code/
│   ├── python/                  # Python implementation
│   │   └── Food_Access_Nutrition_Equity.ipynb
│   ├── r/                       # R implementation
│   │   └── food_access_wrangling.R
│   ├── sql/                     # SQL implementation
│   │   └── food_access_queries.sql
│   └── excel/                   # Excel documentation
│       └── excel_workflow.md
│
├── outputs/
│   └── visualizations/          # Analysis charts and graphs
│
├── docs/
│   ├── project_report.pdf      # Final project report
│   └── data_dictionary.md      # Variable descriptions
│
└── README.md                    # This file
```

## 🚀 Data Wrangling Pipeline

### Phase 1: Data Loading and Inspection
- Load all three datasets
- Examine structure, dimensions, and data types
- Identify initial data quality issues

### Phase 2: Column Selection
- Reduce USDA Atlas from 147 to ~20 columns
- Select relevant demographic variables
- Choose key nutritional indicators

### Phase 3: Data Cleaning
- Handle missing values (NULL, -1, NaN)
- Standardize county and state names
- Clean food item descriptions
- Fix data type inconsistencies

### Phase 4: Data Transformation
- Convert census tracts to county-level aggregations
- Create derived variables (urban/rural flags, accessibility scores)
- Normalize nutritional units
- Categorize foods into groups

### Phase 5: Data Aggregation
- Aggregate tract-level data to county level
- Calculate county-level statistics
- Summarize nutritional profiles by food category

### Phase 6: Data Merging
- Join USDA food access with county demographics
- Match on standardized county names
- Handle unmatched records

### Phase 7: Final Dataset Preparation
- Create three analysis-ready datasets
- Document all transformations
- Export to appropriate formats

### Phase 8: Analysis and Visualization
- Generate research question visualizations
- Create summary statistics
- Validate data integrity

## 🔧 Implementation Details

### Python (pandas)
- **Environment**: Jupyter Notebook
- **Key Libraries**: pandas, numpy, matplotlib, seaborn
- **Approach**: DataFrame operations using .loc[], boolean indexing, groupby aggregations
- **Output Format**: CSV files

### R (tidyverse)
- **Environment**: RStudio
- **Key Packages**: dplyr, tidyr, ggplot2, readr
- **Approach**: Pipe-based workflow with verb functions (filter, select, mutate, group_by)
- **Output Format**: CSV and RDS files

### SQL
- **Platform**: SQLite or PostgreSQL
- **Approach**: CREATE TABLE statements, JOINs, aggregate functions, CTEs
- **Output Format**: Database tables and views

### Excel
- **Version**: Excel 2016 or later
- **Techniques**: Power Query, VLOOKUP, Pivot Tables, Data Validation
- **Output Format**: XLSX workbooks with multiple sheets

## 🎨 Key Wrangling Challenges Addressed

1. **Wide Dataset Reduction**: Reduced 228 total columns to 30 core columns (86.8% reduction)
2. **Geographic Mapping**: Successfully mapped census tracts to counties for Texas
3. **Name Standardization**: Resolved inconsistencies in county and state naming conventions
4. **Missing Data Handling**: Implemented consistent rules for NULL, -1, and NaN values
5. **Food Categorization**: Created logical groupings for 7,000+ food items
6. **Unit Harmonization**: Documented and standardized nutritional measurements

## 🌍 Results Summary

- **Final Datasets**: 3 clean, analysis-ready datasets
- **Texas Focus**: 254 counties analyzed
- **Data Quality**: 100% of missing values handled appropriately
- **Dimension Reduction**: From 228 to 30 columns while preserving analytical value
- **Visualizations**: 5 research question charts generated

## 🤝 Technical Requirements

### Python
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### R
```r
install.packages(c("tidyverse", "readr", "haven"))
```

### SQL
- SQLite 3.x or PostgreSQL 12+

### Excel
- Microsoft Excel 2016+ with Power Query

## 📝 Usage Instructions

1. **Clone the repository**
   ```bash
   git clone [repository-url]
   cd Food_Access_Nutrition_Equity
   ```

2. **Place raw data files in `data/raw/` directory**

3. **Run implementation of choice**:
   - Python: Open and run `Food_Access_Nutrition_Equity.ipynb`
   - R: Source `food_access_wrangling.R`
   - SQL: Execute `food_access_queries.sql`
   - Excel: Follow `excel_workflow.md`

## 📚 Key Findings

- **Weak Correlation**: Poverty rates show surprisingly weak correlation (-0.073) with food access limitations in Texas counties
- **Urban Advantage**: Urban counties consistently show better food accessibility metrics
- **Education Impact**: Higher educational attainment strongly correlates with improved food access
- **Nutritional Diversity**: Significant variation in nutritional profiles across food categories

## 📢 Academic Context

This project was completed as part of a data wrangling course, demonstrating proficiency in:
- Multiple technical platforms
- Real-world data integration
- Reproducible research practices
- Documentation and communication

## 📝 Author

cchitse(Jason C)

## 📝 MIT License

This project is for academic purposes. Data sources retain their original licensing.

## 📝 Acknowledgments

- USDA for Food Access Research Atlas data
- CORGIS project for curated datasets
- Course instructors for methodology guidance

## 📝 References

- [USDA Economic Research Service. (2023). Food Access Research Atlas.](https://www.ers.usda.gov/data-products/food-access-research-atlas/download-the-data)
- [CORGIS Dataset Project. County Demographics](https://corgis-edu.github.io/corgis/csv/county_demographics/)
- [CORGIS Dataset Project. Food Nutrition](https://corgis-edu.github.io/corgis/csv/food/)
- [Howisonlab tutorials for pandas methodology (howisonlab.github.io)](https://howisonlab.github.io/datawrangling/current/python_pandas/python_pandas_intro.html)

---

*Last Updated: November 18, 2025*
