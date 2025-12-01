# Thermal Imaging Data Analysis and Modeling

## Project Overview
This project focuses on the analysis and modeling of thermal imaging data to evaluate the performance of different thermal cameras (FLIR and ICI) in measuring facial temperatures. The goal is to compare the two imaging systems, analyze temperature distributions across various facial regions, and develop machine learning models to classify or predict thermal patterns.

## Project Structure
The project consists of two main Jupyter notebooks:

### 1. Exploratory Data Analysis (`eda.ipynb`)
This notebook handles the initial data ingestion, cleaning, and exploratory analysis.
- **Data Loading**: Reads raw CSV files for FLIR and ICI datasets.
- **Data Cleaning**:
    - Removes empty columns and rows.
    - Standardizes column names (handling suffixes like `_1`, `_2`, etc.).
    - Converts wide-format data to long-format for easier analysis.
- **Data Transformation**: Reshapes data to have a consistent structure with `SubjectID`, `Round`, and various temperature features.
- **Output**: Saves cleaned datasets (`FLIR_cleaned_long.csv`, `ICI_cleaned_long.csv`, etc.) for further use.

### 2. Modeling (`model.ipynb`)
This notebook focuses on predictive modeling using the cleaned data.
- **Data Preparation**: Loads the cleaned long-format CSV files.
- **Feature Engineering**: Prepares features for machine learning models.
- **Modeling**: Utilizes algorithms like **Random Forest Classifier** to analyze the data.
- **Evaluation**: Assesses model performance using metrics such as classification reports, confusion matrices, and accuracy scores.

## Datasets
The project uses two primary datasets:
- **FLIR Dataset**: Thermal data captured using FLIR cameras.
- **ICI Dataset**: Thermal data captured using ICI cameras.

Key features include temperature measurements from various facial regions (e.g., Inner Canthus, Forehead, etc.) across multiple rounds of measurement.

## Prerequisites
To run the notebooks, you need the following Python libraries:
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scipy`
- `scikit-learn`

## Model Performance
Based on hyperparameter tuning, the **Gradient Boosting Regressor** emerged as the best performing model for both cameras.

| Camera | Best Model | Accuracy (R² Score) |
| :--- | :--- | :--- |
| **FLIR** | Gradient Boosting | **0.7532** |
| **ICI** | Gradient Boosting | **0.7452** |

Other models evaluated included Random Forest, Decision Tree, and Support Vector Regressor (SVR).

## Usage
1.  **Setup Environment**: Ensure you have Python installed along with the required libraries. You can install them using pip:
    ```bash
    pip install pandas numpy matplotlib seaborn scipy scikit-learn
    ```
2.  **Run EDA**: Execute `eda.ipynb` first to process the raw data and generate the cleaned CSV files.
3.  **Run Modeling**: Execute `model.ipynb` to train and evaluate the machine learning models using the cleaned data.

## Results
The analysis provides insights into:
- The correlation between FLIR and ICI temperature readings.
- The variability of temperature measurements across different facial regions.
- The effectiveness of machine learning models in distinguishing between different thermal profiles or subjects.
