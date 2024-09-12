# Does Immediate Antibiotic Administration Reduce Sepsis Mortality? A Metaanalysis in R

This repository contains the code and materials for a metaanalysis examining whether the timing of antibiotic administration affects mortality rates among sepsis patients. The analysis expands on the metaanalysis conducted by [Rothroc et al. (2020)](https://www.annemergmed.com/article/S0196-0644(20)30337-1/fulltext#tbl1fnddagger) by incorporating two additional studies published after the original review. The study uses random and fixed effects models to determine the impact of immediate (0-1 hour) versus early (1-3 hours) antibiotic administration on patient outcomes. Additionally, it explores whether various study-specific factors, such as patient demographics, hospital characteristics, and study design, influence effect sizes across different studies.

## Key Features

- **Data Analysis**: Applies both random and fixed effect models to estimate the impact of antibiotic timing on sepsis mortality.
- **Reproducibility**: Uses `renv` to manage the R environment, ensuring reproducibility of the analysis across systems.
- **Visualization**: Includes forest plots to illustrate the results and funnel plots to assess potential publication bias.
- **Extended Dataset**: Incorporates two additional studies ([Siewers et al. (2021)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8119622/) and [Althunayyan et al. (2022)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9280501/)) to extend the original dataset.

## Files

- `sepsis_metaanalysis.qmd`: Quarto markdown document containing the full metaanalysis, including methods, data, and visualizations.
- `images/sepsis_results_org.jpg`: Forest plot with results from original publication
- `images/sepsis_mortality_alth.jpg`: Graph depicting mortatlity rates in groups (Althunayyan et al. (2022))
- `data/sepsis_meta.csv`: The dataset used in the analysis, containing variables such as the number of subjects, events, and study characteristics.
- `renv.lock`: Lock file for managing the R environment via `renv`.
- `README.md`: This file.

## Getting Started

### Prerequisites

To reproduce the analysis, you need R and Quarto installed on your system. The repository uses the `renv` package to manage dependencies. If `renv` is not installed, the script will install it.

### Instructions

1. Clone this repository:
    ```bash
    git clone git@github.com:jjfrackowiak/Sepsis-Antibiotic-Timing-MetaAnalysis.git
    ```
2. Run the Quarto document (`sepsis_meta_analysis.qmd`) to reproduce the analysis:
    ```bash
    quarto render sepsis_metaanalysis.qmd
    ```
    
### Data

The data used in this analysis contains the following key variables:

- **Author**: Study authors.
- **Number_of_Subjects_01**: Number of subjects receiving antibiotics within 0-1 hours.
- **Events_of_Subjects_01**: Number of death events in the 0-1 hour group.
- **Number_of_Subjects_13**: Number of subjects receiving antibiotics within 1-3 hours.
- **Events_of_Subjects_13**: Number of death events in the 1-3 hour group.
- **Number_of_Hospitals**: Number of hospitals involved in the study.
- **Design**: Study design (retrospective, prospective, etc.).
- **Median_Age**: Median age of patients in the study.
- **Percent_Male**: Percentage of male patients.
- **Median_Time_to_Antibiotics**: Median time from sepsis onset to antibiotic administration.

### Results

- **Original Dataset**: Analysis of the original 13 studies showed no significant difference in mortality between immediate and early antibiotic administration.
- **Extended Dataset**: Incorporating two additional studies confirmed the original findings under the random effects model. The common effects model showed a significant result with higher mortality for immediate administration.


This analysis was developed using the `renv` package to ensure reproducibility. All dependencies are captured in the `renv.lock` file. To replicate the analysis, `renv::restore()` is run to recreate the environment on your machine.

## Acknowledgments

This project was created as part of the Reproducible Research project for the **Data Science and Business Analytics programme** at the **Faculty of Economic Sciences, University of Warsaw** during the Summer Semester of 2024.

## Contact

Author: Jan Frąckowiak  
Email: jj.frackowiak2@student.uw.edu.pl
