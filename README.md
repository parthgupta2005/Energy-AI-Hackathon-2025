# Energy A.I. Hackathon 2025 Workflow - Green Bay Frackers

**Authors:**  
- Parth Gupta (Department of Computer Science, CNS)  
- Satvik Duddukuru (Departments of Computer Science and Mathematics, CNS)  
- Joshua Yue (Departments of Computer Science and Mathematics, CNS)  
- Akshat Kumar (Department of Computer Science, CNS)  
- Rashed Alsuhabi (Hildebrand Department of Petroleum and Geosystems, Cockrell School of Engineering)  

**Institution:** The University of Texas at Austin, Austin, Texas, USA  

---

## Executive Summary

1. **Goal:** Predict Grid, Diesel, and CNG energy usage during hydraulic fracturing operations for 50 wells, including uncertainty modeling with 100 realizations for each well.  
2. **Approach:** 
   - Data analytics and evaluation of multiple data sources.  
   - Feature engineering: selection, transformation, and imputation for missing data.  
   - Integration of domain expertise at every step.  
   - Selection, training, and tuning of machine learning models.  
3. **Outcome:** A Python-based data analytics and machine learning workflow to optimize well site selection and parameters to reduce energy use.

---

## Data Description

- **Well Data:** `HackathonData2025.csv` contains data for 1083 unique wells with features such as:
  - Well Name, # Stages, # Clusters, Average Stage Time (Estimated & Actual), Frac Fleet, Target Formation, Field Area, Ambient Temperature, Grid, Diesel, CNG, Fuel Type, and Sand Provider.
- **Testing Data:** `testing.csv` is the test set for making predictions.
- **Solution Format:** Predictions must follow the template in `solution.csv`:
  - Well_ID, Fuel_Type, Estimated Energy Use, and 100 realizations (R_1, R_2, ..., R_100).

---

## Workflow Summary

### 1. **Data Preprocessing**
- Utilized `pandas` and `numpy` for data handling and transformation.
- Addressed missing data with imputation techniques.
- Handled categorical data using `LabelEncoder` for efficient model training.
- Scaled and normalized features for compatibility across different models.

### 2. **Feature Engineering**
- Created new features based on domain expertise to enhance predictive accuracy.
- Applied one-hot encoding for categorical features where necessary.
- Performed correlation analysis to select the most relevant features.

### 3. **Model Selection and Training**
- Experimented with multiple algorithms:
   - **CatBoostRegressor:** Gradient boosting model chosen for its efficiency with categorical data.
   - **Linear Regression:** For baseline comparison.
   - **Support Vector Regressor (SVR):** To test non-linear relationships.
- Employed hyperparameter tuning and cross-validation for optimized performance.

### 4. **Uncertainty Modeling**
- Utilized normal distribution (`scipy.stats.norm`) for uncertainty estimation.
- Generated 100 realizations per well using bootstrapping techniques.

### 5. **Evaluation Metrics**
- Assessed models using:
   - **Mean Squared Error (MSE):** For absolute error measurement.
   - **Mean Absolute Percentage Error (MAPE):** For relative accuracy.
- Visualizations through `seaborn` and `matplotlib` to interpret results effectively.

---

## Required Submissions

- `solution.csv` - Predictions and uncertainty for 50 wells.
- Python Workflow (`Hackathon_Workflow.ipynb`) - Code and explanations.
- Presentation (`xxxx.pptx`) - Following the provided template.

---

## How to Run the Code

1. Clone the repository:
   ```bash
   git clone git@github.com:parthgupta2005/Energy-AI-Hackathon-2025.git
   cd Energy-AI-Hackathon-2025
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the Jupyter notebook:
   ```bash
   jupyter notebook Hackathon_Workflow.ipynb
   ```

---

## Acknowledgments

As students who worked on this project, we would like to express our gratitude to:
- Prof. Michael Pyrcz and Prof. John T. Foster for their guidance and support.  
- Ahmed Merzoug and Elnara Rustamzade for organizing the hackathon and providing valuable resources.  
- The Hildebrand Department of Petroleum and Geosystems Engineering for their continuous support.  

---

