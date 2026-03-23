# Protein Biomarker Statistical Analysis using R

This repository contains a comprehensive statistical analysis of biological datasets, focusing on bacterial growth, enzyme activity, and animal behavior. The analysis is implemented in R and utilizes the Analysis of Variance (ANOVA) framework to derive biological insights.

---

## Project Overview

The project is structured into three experimental modules, each applying specific statistical methodologies to test biological hypotheses.

### 1. Bacterial Doubling Time (One-Way ANOVA)
* [cite_start]**Objective**: To determine if various pollutant treatments (Diesel, Mercury, Pesticide, Cadmium) significantly alter the doubling time of bacteria compared to a control group[cite: 251, 252].
* **Methodology**:
    * [cite_start]**One-Way ANOVA**: Used to compare mean doubling times across five groups[cite: 299, 300].
    * [cite_start]**Bartlett’s Test**: Conducted to verify the assumption of equal variance ($p = 0.5089$)[cite: 292, 298].
    * [cite_start]**Tukey’s HSD**: Applied for post-hoc pairwise comparisons to identify specific differences between groups[cite: 301, 311].

### 2. Enzyme Activity (Two-Way ANOVA)
* [cite_start]**Objective**: To examine the effects of temperature (Low, Medium, High, Ultra High) and different cell batches (A–E) on enzyme activity[cite: 327, 329, 330].
* **Methodology**:
    * [cite_start]**Two-Way ANOVA with Interaction**: Evaluated the main effects of temperature and batch, as well as their interaction (`temp * cellbatch`)[cite: 364, 366].
    * [cite_start]**Interaction Plots**: Utilized to visualize how different cell batches respond to temperature fluctuations[cite: 341, 357].

### 3. Mouse Activity (Model Selection)
* [cite_start]**Objective**: To analyze how time of day (morning, midday, afternoon) and light intensity (low, medium, bright) influence mouse activity levels[cite: 384, 393, 394].
* **Methodology**:
    * [cite_start]**AIC (Akaike Information Criterion)**: Used to compare four different models (time only, light only, additive, and interaction) to identify the best fit for the data[cite: 474, 478, 481].
    * [cite_start]**Assumption Testing**: Included Bartlett’s test for homogeneity of variance and the Shapiro-Wilk test for normality of residuals ($p = 0.5157$)[cite: 450, 452, 456, 460].

---

## Statistical Results Summary

### 1. Bacterial Growth Results
[cite_start]The One-Way ANOVA indicated that the pollutant treatments did not have a statistically significant effect on bacterial doubling time at the $\alpha = 0.05$ level ($F(4, 145) = 1.728, p = 0.147$)[cite: 300]. [cite_start]Tukey HSD post-hoc tests confirmed no significant pairwise differences between any pollutant and the control group[cite: 311, 317, 321].


### 2. Enzyme Activity Results
[cite_start]Temperature was found to be a highly significant factor influencing enzyme activity ($p < 2e-16$)[cite: 371]. [cite_start]However, there was no significant effect from the specific cell batch ($p = 0.790$) or the interaction between temperature and batch ($p = 0.487$)[cite: 375, 378].


### 3. Mouse Activity Model Selection
[cite_start]The AIC analysis determined that the **additive model** (`activity ~ time + light`) was the most appropriate fit for the data, as it yielded the lowest AIC value (381.3962)[cite: 484, 485]. [cite_start]Neither the interaction between time and light nor the main effects themselves reached standard statistical significance in the full model ($p > 0.05$)[cite: 437, 441, 447].

---

## Requirements

To execute the analysis script (`finalSolutions.Rmd`), the following R environment is required:
* **R** (Version 4.0 or higher recommended)
* [cite_start]**ggplot2**: For data visualization and interaction plotting [cite: 240]
* [cite_start]**dplyr**: For data manipulation and summary statistics [cite: 241]
* [cite_start]**knitr**: For rendering the R Markdown document [cite: 239]

---

## Usage

1.  Clone the repository to your local machine.
2.  Open `finalSolutions.Rmd` in **RStudio**.
3.  Ensure the required libraries are installed by running `install.packages(c("ggplot2", "dplyr", "knitr"))`.
4.  Click the **Knit** button to generate a comprehensive HTML report containing all statistical tables and visualizations.
