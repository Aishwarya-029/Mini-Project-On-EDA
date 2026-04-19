```markdown
# Dataset: UK Road Safety Accidents 2015-2017

## Overview
This dataset, sourced from OpenML (data_id=42803), contains detailed information about road safety accidents that occurred in the United Kingdom between 2015 and 2017. It includes a wide range of features related to the accident circumstances, vehicles involved, casualties, and environmental conditions.

## Key Features
The dataset initially comprises 67 features, covering aspects such as:
*   **Accident Details**: `Accident_Index`, `Date`, `Time`, `Location_Easting_OSGR`, `Location_Northing_OSGR`, `Longitude`, `Latitude`, `Police_Force`, `Accident_Severity`, `Number_of_Vehicles`, `Number_of_Casualties`, `Speed_limit`, `Junction_Detail`, `Urban_or_Rural_Area`, `Weather_Conditions`, `Road_Surface_Conditions`, etc.
*   **Vehicle Details**: `Vehicle_Type`, `Age_of_Vehicle`, `Sex_of_Driver`, `Age_of_Driver`, `Journey_Purpose_of_Driver`, `Was_Vehicle_Left_Hand_Drive?`, etc.
*   **Casualty Details**: `Casualty_Class`, `Sex_of_Casualty`, `Age_of_Casualty`, etc.

## Preprocessing Steps Performed
The following steps have been executed to clean and prepare the dataset:
1.  **Initial Loading**: The dataset was loaded using `fetch_openml` into a pandas DataFrame `df_X`.
2.  **Data Type Conversion**: The `Sex_of_Driver` column was converted to `float`.
3.  **Duplicate Handling**: Duplicates were identified (excluding `Accident_Index`) and removed from the dataset.
4.  **Missing Value Treatment**:
    *   Rows with more than 20% missing values were dropped.
    *   Columns with more than 15% missing values were dropped.
5.  **Outlier Removal**: The top 10 most frequent accident IDs were identified and removed as potential data entry errors or anomalies.

## Exploratory Data Analysis (EDA) Highlights
*   **Feature Structure**: Investigation of data types and unique values for both numerical and non-numerical features.
*   **Feature Distributions**: Histograms for numerical features and bar plots for non-numerical feature value counts were generated.
*   **Singular Value Analysis**: Features with a high proportion of a single most frequent value were identified.
*   **Feature Relationships**:
    *   Pair plots were used to visualize relationships among continuous numerical features.
    *   `stripplot` and `violinplot` were employed to examine relationships between discrete/ordinal features and continuous features (e.g., `Age_of_Driver`, `Latitude`).
    *   An interactive scatter plot of `Location_Easting_OSGR` and `Location_Northing_OSGR` was created using `plotly.express`.
*   **Correlation Analysis**: A Pearson correlation matrix was computed for numerical features, and its heatmap was visualized to identify strong, medium, and weak correlations.

## Further Analysis
This cleaned and preprocessed dataset is now ready for further analysis, such as:
*   Predictive modeling (e.g., predicting accident severity).
*   Geospatial analysis of accident locations.
*   Time-series analysis of accident occurrences.
```
