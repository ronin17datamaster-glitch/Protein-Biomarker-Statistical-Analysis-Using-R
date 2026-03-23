# Protein Biomarker Statistical Analysis Using R

## Overview

This project focuses on the statistical analysis of protein biomarker data using R to evaluate the impact of different experimental conditions on biological responses. It applies techniques such as one-way ANOVA, two-way ANOVA, assumption testing, and post-hoc analysis to identify significant patterns and relationships in the data. The analysis is structured into three independent experimental studies.

## Objectives

The objective of this project is to analyze variations in protein-related biological measurements and determine whether different environmental or experimental factors lead to statistically significant changes. It also aims to demonstrate proper statistical methodology, including model validation and interpretation of results.

## Project Description

### 1. Pollutant Impact on Biological Response

This analysis examines how different pollutants influence bacterial doubling time, which serves as a proxy for biological activity related to protein expression. The study includes multiple pollutant types such as Control, Diesel, Mercury, Pesticide, and Cadmium. Exploratory data analysis is performed using boxplots and summary statistics. Bartlett’s test is used to check homogeneity of variances, followed by one-way ANOVA to detect significant differences. Tukey HSD post-hoc analysis identifies specific group-level differences.

### 2. Enzyme Activity Analysis

This section evaluates enzyme activity under varying temperature conditions and across different cell batches. Temperature levels range from Low to Ultra High, and multiple batches are analyzed to capture variability. An interaction plot is used to visualize relationships, and a two-way ANOVA with interaction is conducted to assess both main and interaction effects. This helps determine how protein-related enzyme activity is influenced by multiple factors simultaneously.

### 3. Behavioral Response Analysis

This analysis investigates how environmental conditions such as time of day and light intensity affect activity levels, which can be linked to biological and protein-regulated processes. A two-way ANOVA is applied to evaluate the effects of both factors. Assumptions are tested using Bartlett’s test for equal variances and the Shapiro-Wilk test for normality. Tukey HSD is used for post-hoc comparisons, and AIC is applied for model evaluation.

## Methodology

The project follows a structured workflow including data exploration, visualization, assumption checking, statistical modeling, and interpretation. Visual tools such as boxplots and interaction plots are used to understand data distribution and relationships. Statistical tests are applied systematically to ensure valid and reliable conclusions.

## Technologies Used

The project is implemented in R using libraries such as ggplot2 for visualization and dplyr for data manipulation, along with base R statistical functions. The entire analysis is documented in an R Markdown file to ensure reproducibility.

## Installation

Install the required packages in R before running the project:

```r
install.packages(c("ggplot2", "dplyr"))
```

## Usage

Open the `.Rmd` file in RStudio and execute all code chunks, or use the Knit option to generate the final HTML report. The report contains visualizations, statistical summaries, ANOVA results, and post-hoc analyses.

## Output

The output is an HTML report that includes plots, descriptive statistics, ANOVA tables, assumption test results, and detailed analysis for each experimental study.

## Key Learnings

This project demonstrates the application of statistical techniques to biological data, particularly in the context of protein biomarker analysis. It highlights the importance of validating assumptions, interpreting interaction effects, and presenting results effectively through visualization.

## Conclusion

The analysis shows that experimental conditions have a statistically significant impact on biological responses linked to protein activity. In the pollutant study, certain pollutants clearly slowed bacterial growth compared to the control, indicating that environmental stressors can directly affect biological processes at a measurable level. The post-hoc results highlight that not all pollutants behave equally, with some having a stronger inhibitory effect.

In the enzyme activity analysis, temperature emerged as a critical factor influencing enzyme performance, while variation across cell batches suggests underlying biological or experimental variability. The presence of interaction effects indicates that enzyme response is not uniform across conditions, meaning optimal performance depends on a combination of factors rather than a single variable.

The mouse activity study further reinforces that biological responses are influenced by multiple environmental conditions simultaneously. Both time of day and light intensity significantly affect activity levels, and their interaction suggests that behavioral patterns are context-dependent rather than independent effects.

Overall, the results emphasize that biological systems are highly sensitive to environmental and experimental conditions, with interactions between variables playing a key role. This highlights the importance of using multi-factor statistical models, such as two-way ANOVA, to capture complex relationships and avoid misleading conclusions from single-factor analysis.
