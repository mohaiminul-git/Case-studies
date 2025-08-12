# Household Power Forecasting with State-Space Models

This project, developed entirely in a Jupyter Notebook, focuses on short-term forecasting of household electricity consumption using advanced time series modeling techniques.  

## Overview
The dataset contains hourly aggregated consumption data (from original 15-minute readings) for 33 households with heat pumps. Only the total household load (`HAUSHALT_TOT`) was analyzed. Two smoothing strategies were applied:  
- **v1:** Rolling mean within each day  
- **v2:** Rolling mean across the same weekday-hour (showed better performance)  

## Methods Performed
- **Exploratory Data Analysis (EDA)** to understand consumption patterns across seasons and weekdays.  
- **Feature Analysis with MANOVA** to evaluate the influence of season, weekday, and household differences.  
- **Model Selection** using AIC for choosing the best-fitting multivariate model.  
- **Clustering** of households via Agglomerative Hierarchical Clustering, with silhouette score to determine optimal clusters.  
- **Cluster Assignment** using KNN to place new households into existing groups.  
- **Forecasting** with:
  - **Kalman Filter**
  - **Particle Filter**  
  Both with and without exogenous inputs from cluster-level profiles.
- **Hyperparameter Optimization** through random search, selecting the configuration with the lowest cross-validated RMSE.
- **Model Evaluation** comparing RMSE across all settings.

## Key Findings
- The v2 smoothing method consistently outperformed v1.  
- Using exogenous cluster profiles improved forecast accuracy.  
- Kalman filter achieved lower RMSE than the Particle filter on this dataset.

## How to Use
Open the Jupyter Notebook (`cas_studies_final_clean.ipynb`), ensure the required Python packages are installed, and run all cells in order. The notebook contains data preprocessing, modeling, clustering, forecasting, and evaluation steps in one place.

## Author
Mohaiminul Islam — TU Dortmund, Case Studies (Summer 2023/24)
