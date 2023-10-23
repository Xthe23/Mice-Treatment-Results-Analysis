# Pymaceuticals Inc.

This project focuses on the analysis of data related to Pymaceuticals Inc., a fictitious pharmaceutical company. The primary aim is to understand the results of treatments on mice over time. The dataset comprises of two CSV files: one detailing mouse metadata and the other detailing study results. These are then combined and processed to provide various insights.

Below is a snippet of the `pymaceuticals.ipynb` file used in this project. For the complete code, please [click here](https://github.com/Xthe23/data-visualization/blob/main/Pymaceuticals/pymaceuticals.ipynb).

```python
# Put treatments into a list for for loop (and later for plot labels)
treatments = ['Capomulin', 'Ramicane', 'Infubinol', 'Ceftamin']

# Create empty list to fill with tumor vol data (for plotting)
tumor_volumes = []

# Calculate the IQR and quantitatively determine if there are any potential outliers. 
for treatment in treatments:
    
    # Locate the rows which contain mice on each drug and get the tumor volumes
    subset = final_tumor_volume[final_tumor_volume['Drug Regimen'] == treatment]
    final_tumor_volume_for_treatment = subset['Tumor Volume (mm3)']
    
    # Determine outliers using upper and lower bounds
    quartiles = final_tumor_volume_for_treatment.quantile([.25,.5,.75])
    lowerq = quartiles[0.25]
    upperq = quartiles[0.75]
    iqr = upperq-lowerq
    lower_bound = lowerq - (1.5*iqr)
    upper_bound = upperq + (1.5*iqr)
    
    treatment_outliers = final_tumor_volume_for_treatment[(final_tumor_volume_for_treatment < lower_bound) | (final_tumor_volume_for_treatment > upper_bound)]
    print(f"{treatment} potential outliers: {treatment_outliers}")
```


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
