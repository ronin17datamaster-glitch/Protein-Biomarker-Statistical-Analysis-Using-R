# Protein Biomarker Statistical Analysis using R

This project provides a rigorous statistical evaluation of biological datasets, focusing on bacterial growth dynamics, enzyme activity, and behavioral patterns. The analysis is implemented in R, utilizing the ANOVA framework to test hypotheses across multiple experimental conditions.

---

## Project Overview

The repository contains a structured analysis divided into three primary experimental modules:

### 1. Bacterial Doubling Time (One-Way ANOVA)
* **Objective**: Evaluate the impact of various pollutants (Diesel, Mercury, Pesticide, Cadmium) on the doubling time of bacterial populations relative to a control group.
* **Statistical Methods**:
    * **One-Way ANOVA**: Used to determine if significant differences exist between treatment means.
    * **Bartlett’s Test**: Conducted to confirm the assumption of homogeneity of variance across groups.
    * **Tukey’s HSD**: Applied as a post-hoc measure to identify specific pairwise differences between pollutants and the control.

### 2. Enzyme Activity (Two-Way ANOVA)
* **Objective**: Analyze the dual effects of temperature (Low, Medium, High, Ultra High) and cell batch (A through E) on enzyme activity levels.
* **Statistical Methods**:
    * **Two-Way ANOVA with Interaction**: Evaluates the main effects of temperature and batch, as well as the interaction between the two factors (`temp * cellbatch`).
    * **Interaction Plots**: Generated to visualize how enzyme response to temperature varies across different biological batches.

### 3. Mouse Activity Patterns (Model Selection)
* **Objective**: Investigate the influence of time of day and light intensity on mouse activity, focusing on selecting the most appropriate statistical model.
* **Statistical Methods**:
    * **Akaike Information Criterion (AIC)**: Used for model comparison to select between additive and interaction models.
    * **Shapiro-Wilk Test**: Utilized to verify the normality of residuals, ensuring the validity of the ANOVA results.
    * **Tukey’s HSD**: Employed to investigate significant differences identified within the time and light factors.

---

## Statistical Summary

* **Bacterial Analysis**: The study found statistically significant differences in doubling times ($p = 0.00115$), with Cadmium and Diesel treatments showing the most pronounced deviations from the control.
* **Enzyme Analysis**: Temperature was identified as a highly significant factor ($p < 2e-16$). A marginal interaction was observed between temperature and cell batch ($p = 0.0601$), suggesting batch-specific thermal sensitivity.
* **Behavioral Analysis**: Based on AIC values, the additive model (`activity ~ time + light`) was identified as the superior fit compared to the interaction model, indicating that time of day and light intensity influence activity independently.

---

## Detailed Results of Tukey HSD Post-hoc Analysis

The following tables provide the specific pairwise comparisons for the significant factors identified in the ANOVA models.

### 1. Bacterial Doubling Time (Pollutant vs. Control)
The Tukey HSD test identifies which specific pollutants differ significantly from the baseline control group.

| Comparison | Difference | p-adj | Significance |
| :--- | :--- | :--- | :--- |
| **Diesel - Control** | -3.00 | 0.0122 | Significant |
| **Mercury - Control** | -1.80 | 0.2845 | Not Significant |
| **Pesticide - Control** | -1.53 | 0.4578 | Not Significant |
| **Cadmium - Control** | -4.03 | 0.0010 | Highly Significant |

### 2. Mouse Activity (Time of Day)
As the additive model was selected via AIC, the post-hoc analysis focuses on the main effects of the time periods.

| Comparison | Difference | p-adj | Significance |
| :--- | :--- | :--- | :--- |
| **midday - morning** | 4.14 | 0.0028 | Significant |
| **afternoon - morning** | 3.33 | 0.0215 | Significant |
| **afternoon - midday** | -0.81 | 0.7432 | Not Significant |

### 3. Mouse Activity (Light Intensity)
Pairwise comparisons for the levels of light intensity, independent of the time of day.

| Comparison | Difference | p-adj | Significance |
| :--- | :--- | :--- | :--- |
| **medium - low** | 2.53 | 0.0912 | Not Significant |
| **bright - low** | 3.51 | 0.0125 | Significant |
| **bright - medium** | 0.98 | 0.7144 | Not Significant |

---

## Requirements

The analysis requires the R programming environment and the following packages:
* **ggplot2**: For data visualization and interaction plotting.
* **dplyr**: For data manipulation and group-wise summary statistics.
* **knitr**: For compiling the R Markdown source into a formatted report.

---

## Usage

1. Clone the repository to your local environment.
2. Ensure R and the required libraries (`ggplot2`, `dplyr`) are installed.
3. Open `finalSolutions.Rmd` in RStudio.
4. Execute the "Knit" command to generate the full statistical report, including all visualizations and hypothesis test outputs.
