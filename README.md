# Feature Selection and Random Forest Model Training
Main Script for Methods of Master's Thesis "Assessing Potential Ink Disease Distribution in Sweet Chestnut
Forests in Switzerland. A Remote Sensing Approach"

This repository contains the code used in my Master's Thesis to develop a Random Forest classification model for assessing potential diseased sweet chestnut trees. The model utilizes Recursive Feature Elimination (RFE) and Leave Location Out Cross-Validation (LOO-CV) for feature selection and model validation.

Overview
The primary goal of this project is to classify the condition of trees based on various spectral indices and features. The script performs the following key tasks:

  Data Preprocessing:
        Loading and cleaning of data.
        Feature engineering to create relevant features for model training.

  Model Development:
        Random Forest Classifier: A Random Forest model is used to classify the condition of trees (e.g., healthy vs. symptomatic).
        Recursive Feature Elimination (RFE): RFE is applied to select the most important features for the classification model.

  Cross-Validation:
        Leave Location Out Cross-Validation (LOOCV): The model is validated using LOOCV to ensure generalization across different tree locations.

  Model Evaluation:
        The performance of the model is evaluated using various metrics such as accuracy, precision, recall, and F1-score.

File Structure

├── main_script.py                # The main script for model development
├── data/
│   ├── data.csv                  # Input dataset
├── plots/
│   ├── plot_1.png                # Example plots generated during the analysis
├── README.md                     # Project documentation
├── requirements.txt              # List of required Python packages
└── thesis.pdf                    # Master's thesis PDF (optional)

Requirements

The following libraries are required to run the script:

    pandas
    numpy
    scikit-learn
    matplotlib
    seaborn
    joblib
