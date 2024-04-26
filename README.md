# ECON 442: Source Code and Data
This repository contains the data and script files used (outside of PISA files) to generate the findings in my paper.
I discuss below the main files that are important.

## Build Process
- `build/01_build.ipynb` is the main aggregator for all the datasets
- ARWU data is generated using the 01-04 arwu IPYNB files in the main directory (see ARWU.md for more information)
- `load_worldbank.ipynb` generates the parquet file from the world bank WDI CSVs
- XGBoost code is in `build/xgboost.ipynb`
- PCA and country dummy regression is in `build/furtehr_analysis.ipynb`

## Regressions and Charts
- These are all in the `charts` directory
- `charts/charts.ipynb` generates all the figures used in the presentation and paper
- `charts/regs.ipynb` generates all the regression tables used in the presentation and paper (note they are configured for Latex output right now)
- `charts/panel.ipynb` helps generate some of the panel statistics table presented

## Data
- The main data file used is `data/combined-2022-xgboost-synthetic-eiu.parquet` contains the data which has nulls imputed with XGBoost
- `data/combined-2022-included.parquet` is the non-imputed version

### PISA data source
- Since the earlier PISA files were very hard to work with without SPSS or SAS, I used [Leaning Tower](https://github.com/kevinwang09/learningtower) as a substitute
- Due to the very large sizes, the original files are not included - the main transformation applied was to convert the R files to Parquet format (`PISA_00-18.parquet`)
- 2022 data is included directly from PISA (original files also not included). This is combined with the main data in `build/2022.ipynb`