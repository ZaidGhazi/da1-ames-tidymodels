# Ames Housing Price Prediction with Tidymodels

## Overview
This project builds a reproducible modeling workflow for the Ames Housing price prediction task. It uses feature engineering, preprocessing recipes, regularized regression, and cross-validation to predict home sale prices and generate a submission file.

## Problem Statement
Predict residential sale prices from structured property attributes so that a modeling team can compare regularized linear models and understand which engineered features improve predictive accuracy.

## Key Features
- Tidymodels recipe with imputation, novel-level handling, rare-category pooling, dummy encoding, normalization, and zero-variance filtering.
- Engineered interaction and summary features for lot size, basement and floor area, quality, bathrooms, rooms, garage capacity, and seasonality.
- Natural spline transformation for `GrLivArea` to capture non-linear price behavior.
- Ridge, lasso, and elastic net regression with cross-validated tuning.
- Final predictions exported to `final_submission.csv`.

## Data Source
The analysis uses the Ames Housing train/test files from the project assignment, matching the common Kaggle-style Ames Housing schema with `SalePrice` as the training target. Raw `train.csv` and `test.csv` files are not committed because the source script originally referenced local course files.

## Methods and Tools
- R Markdown
- R, tidymodels, recipes, workflows, tune, glmnet, caret, ggplot2, patchwork
- Regularized regression: ridge, lasso, elastic net
- Five-fold cross-validation and RMSE-based model selection

## How to Run Locally
1. Install R and RStudio or another R-capable editor.
2. Copy `.Renviron.example` to `.Renviron` and update the CSV paths.
3. Place `train.csv` and `test.csv` in `data/` or point the environment variables to your local files.
4. Open `scr.Rmd` and knit it, or run the chunks interactively.

```r
install.packages(c(
  "tidymodels", "caret", "glmnet", "ggplot2", "patchwork"
))
```

## Required Packages
- `tidymodels`
- `caret`
- `glmnet`
- `ggplot2`
- `patchwork`

## Main Files to Review
- `scr.Rmd`: source analysis and modeling workflow.
- `Report.html`: rendered report output.
- `final_submission.csv`: generated prediction submission.
- `Instructions.pdf`: assignment instructions.
- `.Renviron.example`: placeholder local data path configuration.

## Screenshots
Screenshots are not committed yet. Suggested additions:

- `screenshots/eda-saleprice-grlivarea.png`
- `screenshots/regularization-paths.png`
- `screenshots/model-rmse-comparison.png`

## Limitations
- Raw data is not committed, so the report must be rerun after providing local data paths.
- The repository keeps rendered output and final predictions for review, but reproducibility depends on matching the original data files.
- Results may vary if package versions differ from the original analysis environment.

## Future Improvements
- Add a compact model-results table to the README.
- Add screenshots from the rendered report.
- Add a short data dictionary or link to the official Ames Housing feature definitions.

