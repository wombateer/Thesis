# Assessing Potential Ink Disease Distribution in Sweet Chestnut Forests in Switzerland. A Remote Sensing Approach - Main Coding Script

This repository contains the code used in my Master's Thesis to develop a Random Forest classification model for assessing potential diseased sweet chestnut trees by using freely availabe Sentinel-2 data and sampled tree data. The model utilizes Recursive Feature Elimination (RFE) and Leave-Location-Out Cross-Validation (LOO CV) for feature selection and model validation.

## Overview
The primary goal of this script is to classify given pixels of sweet chestnut canopies into either "symptomatic" or " non-symptomatic". Potential input features are monthly calculated median values of 8 spectral bands and 8 vegetation indices. The script performs the following key tasks:

 - Leave Location Out-Cross Validation (LLO CV): Instead of using random splits for model validation, a LLO CV was performed to take into account the spatial dependencies of the input data. 9 spatial folds were defined based on visual assessment of the data's spatial distribution. From each fold, 10 samples were held out of the model training to an independent model testing at the end of the script. Used scoring metrics are the overall accuracy, precision, recall and the F1-score.

 - Feature Selection: To optimise the performance of the classifier, a previous assessment of the number and combination of features was made. After a pre-selection of the 24 most important features by RFE, the performance of the RF model with having different numbers of features (8 to 24) and different feature combinations as an input was evaluated. The feature combination that achieved the highest mean accuracies within 5 iterations was selected for training the final RF model.

- Feature Evaluation: By using an iterative approach of training and evaluating the RF classifier with different numbers and combinations of features, an overall assessment of its performance in regard to the given input features was enabled. Provided were the number of features, the mean accurracies of the model performance, the specific importance values of the selected features and each of the accuracy within the 5 iterations. This enabled a detailed insight into the behaviour of the model under different conditions of input features.

- Random Forest (RF) model training: With the final selection of input features, the RF classifier was trained. The model was stored to ensure consistent results when reusing with new input data. 

The following libraries are required to run the script:

    random
    pandas
    numpy
    collections
    scikit-learn
    joblib




