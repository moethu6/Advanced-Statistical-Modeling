Description for Dataset
# Advanced Statistical Modeling

For the Scisci Net Gender Database, refer to: https://springernature.figshare.com/collections/SciSciNet_A_large-scale_open_data_lake_for_the_science_of_science_research/6076908
This repository contains an ISyE 7401 course project focused on **advanced regression modeling** using the SciSciNet gender dataset.

## Repository Structure

- `Project 7401/Project 7401.Rmd` — main analysis workflow in R Markdown (data cleaning, diagnostics, model selection, and regularization methods).
- `Project 7401/Project-7401.tex` and `Project 7401/Project-7401.log` — LaTeX output artifacts.
- `Project 7401/MoeThu.ProjectReport_7401.docx` — project report export.
- `Project 7401/MoeThu.ProjectPresentation_7401_04212024.pptx` — presentation slides.
- `Project 7401/lm.h.index.c10.infer.txt`, `Project 7401/lm.prod.full.txt`, `Project 7401/lm_prod_h_index_summaries.txt` — saved model output summaries.
- `Project 7401/output.png` — generated figure output.

## Dataset

The analysis references the **SciSciNet Gender Database**.

- Source collection: <https://springernature.figshare.com/collections/SciSciNet_A_large-scale_open_data_lake_for_the_science_of_science_research/6076908>
- Expected input file name in the R Markdown workflow: `scisci_gender.tsv`
- The project script currently reads a sample using:
  - `read.delim("scisci_gender.tsv", nrow = 5000)`

> Note: The dataset file is not committed in this repository. Download it separately from the source above and place it where the R Markdown file can access it.

## Methods Included

The project applies and compares multiple statistical approaches:

- Multiple linear regression
- Interaction and quadratic-term models
- Model diagnostics (VIF, Shapiro-Wilk, Breusch-Pagan, leverage/Cook's distance)
- Subset selection (`leaps`)
- Stepwise AIC (`MASS::stepAIC`)
- Ridge regression (`MASS::lm.ridge`)
- Non-negative Garrote (`nnGarrote`)
- Lasso (`lars`, `glmnet`)

## R Package Dependencies

The R Markdown file loads these libraries:

`knitr`, `kableExtra`, `readr`, `ggplot2`, `dplyr`, `car`, `stats`, `lmtest`, `gghalfnorm`, `faraway`, `MASS`, `caret`, `stargazer`, `quadprog`, `glmnet`, `lars`, `nnGarrote`, `corrplot`, and `leaps`.

## How to Run

1. Install R and the packages listed above.
2. Download `scisci_gender.tsv` from SciSciNet.
3. Place `scisci_gender.tsv` in the working directory used when rendering `Project 7401/Project 7401.Rmd`.
4. Render the report:

```r
rmarkdown::render("Project 7401/Project 7401.Rmd")
```

## Notes

- The analysis uses a 5,000-row sample from the full SciSciNet data for demonstration.
- Some files in this repository are generated artifacts from prior report builds.
