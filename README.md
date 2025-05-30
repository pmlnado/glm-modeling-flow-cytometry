# Generalized Linear Modeling for Flow Cytometry data to Analyze Multivariable Influences on Immune Responses

This repository contains the code and data analysis pipeline used to assess immune responses following tuberculosis (TB) vaccination in mice. The study explores the use of Generalized Linear Models (GLMs) to analyze high-dimensional flow cytometry data, with a focus on activated T cells in the lungs post-Mycobacterium tuberculosis (Mtb) infection.

GLMs were used to evaluate the effects of sex, vaccine type, and days post-infection on immune cell phenotype probabilities, addressing non-normality and other violations of classical statistical assumptions. This framework provides a flexible, robust approach for modeling complex immunological data and supports the discovery of critical factors influencing vaccine efficacy.

R code and associated data (excluding raw `.fcs` files) are released under an MIT License. If you use the R code and/or data from this repository, please cite:

**Maldonado et al.** *Modeling Immunity: Generalized Linear Modeling to Analyze Multivariable Influences on Immune Responses in Tuberculosis Vaccine Research * (in preparation). [link]

---

## Project Overview

This repository includes data and code from a murine tuberculosis vaccine study. Mice were vaccinated with one of the following:

- **Saline (control)**
- **BCG**
- **ID93 + GLA-SE**
- **BCG + ID93 + GLA-SE**

Mice were subsequently infected with *Mycobacterium tuberculosis* and immune responses were assessed at **14**, **56**, and **90** days post-infection. Both male and female mice were included in the study.

Flow cytometry was used to quantify leukocytes from lung samples. This repository provides the full GLM framework in R, from data preprocessing to visualization and statistical testing.

---

## Repository Directory


├── Base_period_Treg/         # Folder containing raw CSV files by condition
├── analysis.Rmd              # Full R Markdown analysis script
├── output/                   # (Optional) Directory for saving plots and outputs
└── README.md                 # This file


## Key Analyses Performed

- **Mosaic plots**: Distribution of sex and vaccine groups  
- **Histograms**: Activated CD8⁺ T-cell count distributions  
- **Boxplots**: Proportion of CD3⁺CD4⁻CD8⁺ T cells across vaccine groups and sex  
- **Shapiro-Wilk tests**: Assessing normality of data  
- **Levene’s tests**: Testing homogeneity of variances  
- **Proportion calculations**: Based on parent populations from flow cytometry
- **GLM fitting**: Based on selected variables 
- **Outlier Testing**: Using Cook's distance 
- **Probability Analysis**: Using built in R functions
- **Odds Ratio analysis**: Using built in R functions

---

## Data Availability

Raw `.csv` files containing flow cytometry gate counts are located in the `Base_period_Treg/` directory. These were exported from `.fcs` files generated on the a Cytek Aurora and FlowJo.

Due to file size limitations, `.fcs` files are not included in this repository. To request access to raw `.fcs` files, please contact Pablo at p.maldonado@colostate.edu.

---

## Software and Dependencies

This analysis was performed in **R** using the following packages:


library(readr)
library(readxl)
library(tidyverse)
library(jtools)
library(ggplot2)
library(ggpubr)
library(ggbeeswarm)
library(ggmosaic)
library(car)
library(rstatix)
library(emmeans)
library(GGally)
library(scales)
library(stringr)
library(kableExtra)
library(multcomp)
library(broom)
library(viridis)
library(writexl)

---
## License
This project is licensed under the MIT License. See the LICENSE file for details.

---
## Contact
For questions, data access, or collaboration inquiries, please contact:
Pablo Maldonado
Henao Lab, Colorado State University
p.maldonado@colostate.edu
