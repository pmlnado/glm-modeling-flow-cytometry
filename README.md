# T-Cell Activation Analysis: Evaluating Vaccine-Induced Immune Responses in Mice

This repository contains the code used to analyze flow cytometry data and generate figures for a project evaluating the immune response to tuberculosis vaccination in mice. The study focuses on CD8⁺ T-cell activation (CD3⁺CD4⁻CD8⁺) across different vaccine formulations and biological sexes over time.

R code and associated data (excluding raw `.fcs` files) are released under an MIT License. If you use the R code and/or data from this repository, please cite:

**[Your Name].** *T-Cell Activation Analysis: Evaluating Vaccine-Induced Immune Responses in Mice* (2025). [Include DOI or preprint link if available.]

---

## Project Overview

This repository includes data and code from a murine tuberculosis vaccine study. Mice were vaccinated with one of the following:

- **Saline (control)**
- **BCG**
- **ID93 + GLA-SE**
- **BCG + ID93 + GLA-SE**

Mice were subsequently infected with *Mycobacterium tuberculosis* and immune responses were assessed at **30**, **60**, and **90** days post-infection. Both male and female mice were included in the study.

Flow cytometry was used to quantify activated T cells (CD3⁺CD4⁻CD8⁺) from lung samples. This repository provides the full R analysis pipeline, from data preprocessing to visualization and statistical testing.

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

---

## Data Availability

Raw `.csv` files containing flow cytometry gate counts are located in the `Base_period_Treg/` directory. These were exported from `.fcs` files generated on the BD LSRFortessa using FlowJo.

Due to file size limitations, `.fcs` files are not included in this repository. To request access to raw `.fcs` files, please contact [Your Name] at [Your Email].

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
