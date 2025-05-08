# Analyzing Population Dynamics and Health Indicators in Malaysia

## Introduction

This project explores key demographic and health trends in Malaysia using multiple official datasets. The analysis focuses on fertility rates, life expectancy, mortality, and population distribution by age and ethnicity. These insights aim to support data-driven decisions in population planning, healthcare, and sustainable development policies.

## Datasets Used

Four datasets sourced from OpenDOSM were analyzed:

1. **Life Expectancy at Birth by Ethnic Group and Sex**  
   - Contains yearly average life expectancy segmented by sex and ethnic group.

2. **Main Demographic Rates**  
   - Includes metrics like crude birth and death rates, fertility rates, and mortality rates (infant, maternal, etc.).

3. **Population by Age Group**  
   - Presents yearly population distribution across defined age ranges.

4. **Age-Specific Fertility Rate and Total Fertility Rate**  
   - Offers detailed fertility rates by age group and total fertility across sex and ethnic group.

## Research Questions

The project addresses various questions, including:
- How has Malaysia's total fertility rate changed over time?
- How does life expectancy differ by ethnic group?
- What trends exist in birth/death rates, and how are they related to fertility and mortality?
- How is the age structure of the population evolving?
- Can fertility or birth rates be predicted using regression models?

## Methodology

### Data Preparation
- Datasets were loaded and cleaned using Pandas.
- Columns were renamed, missing values were handled, and data types standardized.
- Individual datasets were merged or filtered as needed for specific analyses.

### Exploratory Data Analysis
- Time-series plots were used to examine trends in birth, death, fertility, and mortality rates.
- Grouped visualizations revealed age and ethnic distributions.
- Correlation analysis explored relationships between demographic indicators.

### Predictive Modeling
- **Linear Regression** was used to model the crude birth rate.
- **Random Forest Regression** was used to predict total fertility rate.
- Feature importance and forecast trends were visualized to support interpretation.

## Key Insights

- **Total Fertility Rate** in Malaysia has shown a steady decline, aligning with global trends.
- **Life Expectancy** varies across ethnic groups, with some disparities evident over time.
- The **population is aging**, as shown by shifts in the age group distributions.
- **Crude birth rate and fertility rate** are positively correlated.
- Predictive models provided forecasts of fertility rates up to 2030.

## Conclusion

This analysis provides a comprehensive overview of Malaysia’s population and health trends using open data. It highlights the importance of continuous demographic monitoring and supports evidence-based planning. Predictive models offer a foundation for more advanced forecasting and can assist in evaluating policy impacts.

