# Real-Time ROP Prediction with Explainable Machine Learning
## A Random Forest–SHAP Framework for Drilling Optimization

### Project Overview
This repository contains a machine learning framework designed for real-time Rate of Penetration (ROP) prediction. The study focuses on balancing high predictive accuracy with model transparency using **Random Forest** and **SHAP (SHapley Additive exPlanations)**. 

By utilizing raw operational data from the **Utah FORGE geothermal project**, this framework identifies the key mechanical and thermal drivers of drilling efficiency without requiring complex physics-based feature engineering.

### Dataset
The model utilizes the **Well 58-32 Processed Pason Log** provided by the Utah FORGE repository.
*   **Resolution:** Downscaled to ~0.3m (1 ft) intervals [1].
*   **Source:** [GDR OpenEI - Utah FORGE Drilling Data](https://gdr.openei.org/files/1113/Well_58-32_processed_pason_log.csv).
*   **Key Parameters:** Weight on Bit (k-lbs), Rotary Speed (rpm), Surface Torque (psi), Pump Pressure (psi), and Temperature Out (degF).

### Framework Workflow
1. **Data Cleaning:** Handling sensor anomalies (e.g., negative Wellhead Pressure readings and Flow Out offsets).
2. **EDA:** Correlation analysis of mechanical energy inputs vs. ROP.
3. **Model Training:** Primary implementation using Random Forest with LightGBM as a benchmark.
4. **Explainability:** Utilizing SHAP values to provide "feature importance" that aligns with field engineering experience.

### Key Features
- **Simplicity:** Relies on raw operational data, avoiding the need for expert-crafted features like MSE.
- **Transparency:** SHAP interpretations explain *why* the model predicts a specific ROP at a specific depth.
- **Geothermal Insights:** Includes thermal parameters (`Temp In/Out`) unique to geothermal hard-rock drilling.

### Repository Structure
├── data/               # Link to Utah FORGE Well 58-32 CSV

├── notebooks/          # VS Code Jupyter Notebooks for EDA and Model Building

├── src/                # Python scripts for data cleaning and SHAP analysis

├── results/            # Performance metrics (MAE, RMSE, R²) and SHAP plots

└── README.md
