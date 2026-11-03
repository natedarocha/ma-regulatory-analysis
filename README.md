# M&A Deal Dynamics & Regulatory Scrutiny Analyzer

A Python research project exploring the relationship between recorded
regulatory involvement and M&A deal timelines.

## Overview

This project examines whether M&A transactions with recorded antitrust
or foreign-investment regulatory dates tend to have longer
announcement-to-outcome timelines, and whether recorded regulatory
involvement is associated with different completion outcomes.

The analysis was conducted using transaction-level data exported from
Bloomberg. The underlying dataset is licensed and is not included in
this repository.

## Research Approach

The Jupyter notebook cleans and prepares the transaction data, converts
relevant dates and numerical fields, and calculates deal duration as the
number of days between announcement and completion or termination.

It then explores differences in deal timelines and outcomes across
transactions with and without recorded regulatory dates. The statistical
analysis includes a Mann--Whitney U test to compare deal-duration
distributions, Fisher's exact test to examine completion outcomes, and
multivariable OLS regression using log-transformed deal duration and HC3
heteroskedasticity-robust standard errors. Additional specifications and
sensitivity checks examine whether the regression findings are robust to
alternative year controls and the exclusion of the largest transactions
by deal value.

## Definitions and Limitations

**Deal duration** refers to the calendar days between a transaction's
announcement date and its recorded completion or termination date.
**Recorded regulatory involvement** is an indicator based on whether a
relevant regulatory date appears in the dataset. A blank regulatory-date
field does not necessarily mean that a transaction received no
regulatory scrutiny.

The project measures the overall time between announcement and outcome,
not the duration of a regulatory review itself. The analysis is
observational, so its results identify associations and should not be
interpreted as proof that regulatory involvement causes longer deal
timelines or changes the likelihood of completion. Different tests and
models may also use different samples because of missing data and
model-specific requirements.

## Repository Contents

``` text
ma-regulatory-analysis/
├── ma_regulatory_analysis.ipynb
├── README.md
└── requirements.txt
```

The notebook contains the data preparation, statistical analysis,
regression models, and robustness checks. The `requirements.txt` file
lists the Python libraries needed to run it.

## Tools

Python, Jupyter Notebook, pandas, NumPy, Matplotlib, Seaborn, SciPy, and
statsmodels.

Install the required libraries with:

``` bash
pip install -r requirements.txt
```

## Data and Reproducibility

The analysis was developed using licensed Bloomberg M&A transaction
data. The original export and cleaned transaction-level dataset are not
distributed in this repository. Running the notebook requires authorized
access to the data and a locally supplied input file in the expected
format.

## Development Note

I developed this project with assistance from ChatGPT and Claude, using
these tools to support coding, debugging, and the development of the
analytical workflow. I reviewed and adapted the code and analysis as
part of the project.

------------------------------------------------------------------------

Independent research project exploring the intersection of M&A,
financial data analysis, and antitrust regulation.
