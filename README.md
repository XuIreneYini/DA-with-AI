# Analyzing Financial Satisfaction and Perception of Corruption

## Project Purpose
The purpose of this project is to analyze the relationship between financial satisfaction and perception of corruption. The analysis aims to uncover how an individual's financial well-being may correlate with their view on corruption in public institutions.

## Dataset Information
- **Dataset Location:** Local machine
- **Dataset Path:** `data/dataset.csv`
- **Description:** The dataset contains survey responses with various socio-economic and demographic variables. It includes measures of financial satisfaction, perception of corruption, income, education, and other relevant factors that allow for a comprehensive analysis of the research question.

## Selected Variables for Analysis
A total of 8 relevant variables were chosen to provide context and support the analysis:

1. **FinancialSatisfaction:** Measures the respondent’s satisfaction with their financial situation.
2. **PerceptionOfCorruption:** An index reflecting how respondents perceive corruption within public institutions.
3. **Income:** The respondent’s income level.
4. **Age:** The age of the respondent.
5. **Education:** The highest level of education attained by the respondent.
6. **EmploymentStatus:** The current employment status.
7. **Gender:** The respondent’s gender.
8. **Region:** The geographic region of the respondent.

For detailed descriptive analysis, the following 5 variables were selected as the most important:
- **FinancialSatisfaction**
- **PerceptionOfCorruption**
- **Income**
- **Age**
- **Education**

## Descriptive Statistics for Selected Variables

Below is an illustrative table of descriptive statistics for the five key variables. (Note: The values provided are for demonstration purposes; actual results will depend on the dataset.)

| Statistic               | FinancialSatisfaction | PerceptionOfCorruption | Income  | Age    | Education |
|-------------------------|-----------------------|------------------------|---------|--------|-----------|
| **Count**               | 1000                  | 1000                   | 1000    | 1000   | 1000      |
| **Mean**                | 3.5                   | 4.2                    | 45000   | 35     | 14        |
| **Std Dev**             | 1.2                   | 1.8                    | 15000   | 10     | 2         |
| **Minimum**             | 1                     | 1                      | 10000   | 18     | 8         |
| **25th Percentile**     | 2.5                   | 3.5                    | 35000   | 28     | 13        |
| **Median (50th Perc.)** | 3.5                   | 4.0                    | 45000   | 35     | 14        |
| **75th Percentile**     | 4.5                   | 5.0                    | 55000   | 42     | 15        |
| **Maximum**             | 5                     | 7                      | 100000  | 70     | 20        |

## Code for Data Analysis

Below is the Python code used to load the dataset and generate the descriptive statistics table for the selected variables.

```python
import pandas as pd

# Define the dataset path
dataset_path = "data/dataset.csv"

# Load the dataset
df = pd.read_csv(dataset_path)

# Print available columns to verify variables
print("Columns in dataset:", df.columns.tolist())

# Define all relevant variables (8 variables)
variables = [
    'FinancialSatisfaction', 
    'PerceptionOfCorruption', 
    'Income', 
    'Age', 
    'Education', 
    'EmploymentStatus', 
    'Gender', 
    'Region'
]

# For detailed analysis, select the 5 most important variables
selected_vars = ['FinancialSatisfaction', 'PerceptionOfCorruption', 'Income', 'Age', 'Education']

# Generate descriptive statistics for the selected variables
desc_stats = df[selected_vars].describe()

# Display the descriptive statistics table
print("Descriptive Statistics for Selected Variables:")
print(desc_stats)
