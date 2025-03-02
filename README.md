# Analyzing Financial Satisfaction and Perception of Corruption

## Project Purpose
This project analyzes the relationship between financial satisfaction and the perception of corruption. The goal is to understand how individuals' financial well-being correlates with their views on corruption in public institutions.

## Dataset Information
- **Dataset Location:** Local machine
- **Dataset Path:** `D:\winter  term\DA AI\WVS_subset.csv`
- **Description:**  
  The dataset is a subset from the World Values Survey containing responses from 3036 observations. It includes various socio-economic and demographic variables along with responses to survey questions. For this analysis, we focus on selected variables related to financial satisfaction, perception of corruption, income, age, and education.

### Key Variable: B_COUNTRY
- **B_COUNTRY:** This variable indicates the country code for the survey respondent. In this dataset, the value **156** corresponds to **China**.  
  *Note: This ensures the proper identification of respondents from China.*

## Selected Variables for Analysis
Eight variables were initially chosen to build a robust framework; however, for detailed descriptive analysis, we focus on the five most critical variables:
  
1. **Financial Satisfaction (Q10):** Measures the respondent’s satisfaction with their financial situation.
2. **Perception of Corruption (Q11):** Captures respondents’ views on the level of corruption in public institutions.
3. **Income (Q12):** Represents the respondent’s income level.
4. **Age (S025):** Indicates the age of the respondent.
5. **Education (S018):** Records the highest level of education attained by the respondent.

## Descriptive Statistics for Selected Variables

Below is an illustrative table of descriptive statistics for the five key variables. The count reflects the 3036 observations in the dataset. (The numerical values shown are for demonstration purposes; actual results will depend on the dataset.)

| Statistic               | Q10 (Financial Satisfaction) | Q11 (Perception of Corruption) | Q12 (Income) | S025 (Age) | S018 (Education) |
|-------------------------|------------------------------|-------------------------------|--------------|------------|------------------|
| **Count**               | 3036                         | 3036                          | 3036         | 3036       | 3036             |
| **Mean**                | 3.5                          | 4.2                           | 45000        | 35         | 14               |
| **Std Dev**             | 1.2                          | 1.8                           | 15000        | 10         | 2                |
| **Minimum**             | 1                            | 1                             | 10000        | 18         | 8                |
| **25th Percentile**     | 2.5                          | 3.5                           | 35000        | 28         | 13               |
| **Median (50th Perc.)** | 3.5                          | 4.0                           | 45000        | 35         | 14               |
| **75th Percentile**     | 4.5                          | 5.0                           | 55000        | 42         | 15               |
| **Maximum**             | 5                            | 7                             | 100000       | 70         | 20               |

## Code for Data Analysis

Below is the Python code used to load the dataset and generate descriptive statistics for the selected variables.

```python
import pandas as pd

# Define the dataset path (using a raw string to handle backslashes)
dataset_path = r"D:\winter  term\DA AI\WVS_subset.csv"

# Load the dataset
df = pd.read_csv(dataset_path)

# Optional: Strip whitespace from column names in case they exist
df.columns = df.columns.str.strip()

# Print columns to verify the variable names
print("Columns in dataset:", df.columns.tolist())

# Define the 8 relevant variables for the overall project (including additional context variables)
variables = [
    'B_COUNTRY',        # Country code (156 indicates China)
    'B_COUNTRY_ALPHA',  
    'S025',             # Age
    'S018',             # Education
    'Q10',              # Financial Satisfaction
    'Q11',              # Perception of Corruption
    'Q12',              # Income
    'Q1'                # (Example additional variable, e.g., Employment Status or similar)
]

# For detailed analysis, select the 5 most important variables
selected_vars = ['Q10', 'Q11', 'Q12', 'S025', 'S018']

# Generate descriptive statistics for the selected variables
desc_stats = df[selected_vars].describe()

# Display the descriptive statistics table
print("Descriptive Statistics for Selected Variables:")
print(desc_stats)
