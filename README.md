# Pymaceuticals Inc.

Overview
This project focuses on the analysis of data related to Pymaceuticals Inc., a fictitious pharmaceutical company. The primary aim is to understand the results of treatments on mice over time. The dataset comprises of two CSV files: one detailing mouse metadata and the other detailing study results. These are then combined and processed to provide various insights.

# Dependencies and Setup

Python Libraries: matplotlib, pandas, and scipy
Data Files: Mouse_metadata.csv and Study_results.csv

# Data Processing

Loading data from CSV files into pandas DataFrames.
Merging data on "Mouse ID".
Previewing the combined data.
Checking and handling duplicate data.
Cleaning data by removing duplicate mouse IDs.

# Statistical Analysis

Summary statistics on tumor volume for each drug regimen.
Advanced aggregation method to generate summary statistics.

# Data Visualization

Bar plots showcasing the total number of observed mouse timepoints for each drug regimen.
Pie charts depicting the distribution of female versus male mice.
Box plots showcasing the distribution of final tumor volume for specific treatments.
Line plots of tumor volume vs. time point for mice treated with Capomulin.
Scatter plots for mouse weight vs. average observed tumor volume.

# Correlation and Regression

Pearson correlation between mouse weight and average tumor volume.
Linear regression model to predict tumor volume based on mouse weight.
