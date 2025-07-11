## Dataset

**Source**: PISA (Programme for International Student Assessment)  
**Country**: Indonesia  
**Domain**: Science Achievement  
**Sample Size**: Post-cleaning sample varies based on data completeness

### Key Variables

- **Dependent Variable**:
  - `PV1SCIE` to `PV10SCIE`: Ten plausible values for science achievement scores
  
- **Independent Variables**:
  - `ESCS`: Economic, Social and Cultural Status index
  - `ST005Q01JA`: Mother's education level (1-5 scale)
  - `ST007Q01JA`: Father's education level (1-5 scale)
  
- **Weighting Variables**:
  - `W_FSTUWT`: Final student weight
  - `W_FSTURWT1` to `W_FSTURWT80`: Replicate weights for variance estimation

## Methodology

### Data Preprocessing
- Filtered valid responses for parental education variables
- Converted all relevant variables to numeric format
- Removed missing values from critical variables
- Applied PISA survey design considerations

### Statistical Approach
- **Weighted Analysis**: Utilized PISA student weights to ensure representative estimates
- **Plausible Values**: Processed all 10 plausible values for science scores
- **Variance Estimation**: Implemented Balanced Repeated Replication (BRR) with 80 replicate weights
- **Confidence Intervals**: Calculated 95% confidence intervals for all estimates

### Analysis Components

1. **Descriptive Statistics**
   - Weighted means and standard errors for all variables
   - 95% confidence intervals for population estimates

2. **Normality Testing**
   - Shapiro-Wilk test for science score distribution
   - Visual diagnostics (histograms, Q-Q plots)

3. **Regression Analysis**
   - Weighted Ordinary Least Squares (OLS) regression
   - Multiple regression with socioeconomic and parental education predictors
   - Proper handling of PISA's complex survey design

4. **Data Visualization**
   - Scatter plots and regression lines
   - Box plots for categorical variables
   - Distribution visualizations

## Key Findings

### Descriptive Results
- **Science Achievement**: Weighted mean science scores with 95% confidence intervals
- **Socioeconomic Status**: Distribution and central tendency of ESCS index
- **Parental Education**: Prevalence of different education levels

### Regression Results
The analysis reveals the relationship between:
- Socioeconomic status (ESCS) and science achievement
- Maternal education level and student performance
- Paternal education level and academic outcomes

*Note: Specific coefficient values and significance tests are detailed in the analysis notebook.*

## Technical Implementation

### Libraries Used
```python
pandas          # Data manipulation and analysis
numpy           # Numerical computations
scipy.stats     # Statistical tests and distributions
statsmodels     # Regression analysis and statistical modeling
matplotlib      # Basic plotting and visualization
seaborn         # Advanced statistical visualizations
```

### Key Functions
- `weighted_mean()`: Calculates survey-weighted means
- `weighted_ols()`: Performs weighted regression analysis
- Custom BRR implementation for variance estimation

## Files Structure

```
├── M_RISYAD_RAFLAN_20240200004_UAS_STATISTIKA.ipynb  # Main analysis notebook
├── DATA_INDONESIA.xlsx                               # Original PISA 2018 data
├── data_clean.xlsx                                   # Cleaned dataset
└── README.md                                         # Project documentation
```

## Reproducibility

### Requirements
- Python 3.7+
- Jupyter Notebook or JupyterLab
- Required packages (see imports in notebook)

### Running the Analysis
1. Ensure all required libraries are installed
2. Place the PISA 2018 Indonesia dataset (`DATA_INDONESIA.xlsx`) in the project directory
3. Run the notebook cells sequentially
4. Cleaned data will be automatically saved as `data_clean.xlsx`

## Methodological Notes

### Survey Design Considerations
- **Weighting**: All analyses properly account for PISA's complex sampling design
- **Plausible Values**: Multiple imputation approach correctly handles measurement uncertainty
- **Variance Estimation**: BRR method provides accurate standard errors for survey data

### Statistical Assumptions
- Normality of residuals assessed through diagnostic tests
- Linearity assumptions evaluated through visual inspection
- Independence assumption satisfied through proper weighting


## Author

**M. Risyad Raflan**  
Student ID: 20240200004  
Course: Statistics (UAS)