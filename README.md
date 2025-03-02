# Research Project on Trust in Government and Life Satisfaction in China

## 1. Overview and Research Question
**Research Question:**  
> *How does confidence in governmental institutions relate to individuals’ overall life satisfaction in China?*

This research question explores whether varying levels of confidence in government and related institutions correlate with Chinese respondents’ sense of well-being and satisfaction. We will focus on data from the World Values Survey (WVS) Wave 7, specifically the subset in which `B_COUNTRY = 156` (China).

## 2. Key Information About the Dataset
- **Dataset Name:** World Values Survey Wave 7 (Subset)
- **File Name and Path:** `/mnt/data/WVS_subset.csv`
- **Description:**  
  The World Values Survey (WVS) is a global research project that explores people’s values, beliefs, and cultural norms in over 80 societies. In Wave 7 (2017–2022), respondents were surveyed on a wide range of topics including trust, political participation, life satisfaction, economic values, religion, demographics, and more.  
- **Country Filter:** For this project, we only use observations where `B_COUNTRY = 156` (China).

## 3. Variables Selected (10–25 Variables)

Below is a list of 15 variables we consider most relevant to our research question on the relationship between trust in government and life satisfaction in China, along with short descriptions (based on the WVS codebook).  

1. **Q49**: Satisfaction with your life  
   - *Range:* 1 (Completely dissatisfied) to 10 (Completely satisfied)  
   - *Rationale:* Our primary outcome measure of life satisfaction.

2. **Q50**: Satisfaction with financial situation of household  
   - *Range:* 1 (Dissatisfied) to 10 (Satisfied)  
   - *Rationale:* Used as a control for household economic well-being, which can affect both trust and satisfaction.

3. **Q71**: Confidence in the government (in your nation’s capital)  
   - *Range:* 1 (A great deal) to 4 (None at all)  
   - *Rationale:* Our main independent variable capturing trust/confidence in government.

4. **Q73**: Confidence in Parliament  
   - *Range:* 1 (A great deal) to 4 (None at all)  
   - *Rationale:* Another governmental institution that may influence overall trust.

5. **Q70**: Confidence in the Justice System/Courts  
   - *Range:* 1 (A great deal) to 4 (None at all)  
   - *Rationale:* Confidence in the rule of law can affect perceived legitimacy of the government.

6. **Q69**: Confidence in the police  
   - *Range:* 1 (A great deal) to 4 (None at all)  
   - *Rationale:* Another institutional trust measure that can affect how respondents perceive social stability.

7. **Q57**: Most people can be trusted (generalized social trust)  
   - *Range:* 1 (Most people can be trusted) or 2 (Need to be very careful)  
   - *Rationale:* Measures general trust, which might correlate with both government confidence and life satisfaction.

8. **Q48**: Freedom of choice and control  
   - *Range:* 1 (None at all) to 10 (A great deal)  
   - *Rationale:* A subjective control measure that can influence satisfaction.

9. **Q47**: State of health (subjective)  
   - *Range:* 1 (Very good) to 5 (Very poor)  
   - *Rationale:* Self-reported health can be a confounding variable in life satisfaction studies.

10. **Q260**: Age  
   - *Range:* Numeric  
   - *Rationale:* Standard demographic measure.

11. **Q262**: Sex (Respondent’s gender)  
   - *Range:* 1 (Male) or 2 (Female)  
   - *Rationale:* Standard demographic measure.

12. **Q275**: Highest educational level attained  
   - *Range:* Various codes  
   - *Rationale:* Education often influences political attitudes and life satisfaction.

13. **Q288**: Scale of incomes  
   - *Range:* 1 (Lowest group) to 10 (Highest group)  
   - *Rationale:* Another proxy for respondent’s socioeconomic status (besides Q50).

14. **Q288R** (if present) or **Q287**: Income group or Employment status  
   - *Range:* Varies  
   - *Rationale:* Additional socioeconomic/demographic data.

15. **Q56**: Standard of living compared with parents  
   - *Range:* 1 (Better off) to 3 (About the same) or 2 (Worse off)  
   - *Rationale:* Perceived upward or downward mobility could factor into trust and satisfaction.

## 4. Descriptive Statistics for 5 Selected Variables

We highlight five core variables as especially crucial:

1. **Q49**: Life Satisfaction (1–10)  
2. **Q71**: Confidence in Government (1–4)  
3. **Q57**: Generalized Trust (1 or 2)  
4. **Q50**: Satisfaction with Financial Situation (1–10)  
5. **Q260**: Age (numeric)

### Table: Basic Descriptive Statistics

| Variable                         | Count   | Mean    | Std Dev  | Min    | 25%    | 50%    | 75%    | Max    |
|----------------------------------|--------:|--------:|--------:|-------:|-------:|-------:|-------:|-------:|
| **Q49 (Life Satisfaction)**      | 3036    | 7.3798  | 2.1246  | -2.0000 | 6.0000  | 8.0000  | 9.0000  | 10.0000 |
| **Q71 (Confidence in Government)** | 3036    | 1.5511  | 0.6296  | -2.0000 | 1.0000  | 2.0000  | 2.0000  | 4.0000  |
| **Q57 (Generalized Trust)**      | 3036    | 1.3159  | 0.5683  | -2.0000 | 1.0000  | 1.0000  | 2.0000  | 2.0000  |
| **Q50 (Financial Satisfaction)** | 3036    | 6.4931  | 2.3208  | -2.0000 | 5.0000  | 7.0000  | 8.0000  | 10.0000 |
| **Q260 (Age)**                   | 3036    | 1.5491  | 0.4977  |  1.0000 | 1.0000  | 2.0000  | 2.0000  | 2.0000  |




## 5. References
- World Values Survey Association (2022). **World Values Survey Wave 7 (2017-2022) Official Questionnaire and Codebook.**  
- [WVS Official Website](http://www.worldvaluessurvey.org/)

---

## **Code Example (Python)**

```python
import pandas as pd

# 1. Load data
data_path ="D:\winter  term\DA AI\WVS_subset.csv"
df = pd.read_csv(data_path)

# 2. Filter for China only (B_COUNTRY == 156)
df_china = df[df["B_COUNTRY"] == 156]

# 3. Select the variables of interest
vars_of_interest = ["Q49", "Q71", "Q57", "Q50", "Q260"]
subset_china = df_china[vars_of_interest].copy()

# 4. Descriptive statistics
descriptive_stats = subset_china.describe()

print(descriptive_stats)
