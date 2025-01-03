# Assessing Potential Ink Disease Distribution in Sweet Chestnut Forests in Switzerland. A Remote Sensing Approach - Main Coding Script

This repository contains the code used in my Master's Thesis to develop a Random Forest classification model for assessing potential diseased sweet chestnut trees by using freely availabe Sentinel-2 data and sampled tree data. The model includes Recursive Feature Elimination (RFE) and Leave-Location-Out Cross-Validation (LOO CV) for feature selection and model validation.

## Key Tasks
The primary objective of this script is to find the best performing RF model that classifies pixels of sweet chestnut canopies as either "symptomatic" or " non-symptomatic". Potential input features include monthly calculated median values of DN values of 8 spectral bands, as well values from 8 vegetation indices. The script performs the following key tasks:

 - Leave Location Out-Cross Validation (LLO CV): Instead of using random splits for model validation, I used a LLO CV to take into account the spatial dependencies of the input data. 9 spatial folds were defined based on visual assessment of the data's spatial distribution. From each fold, 10 samples were held out from the model training for independent model testing at the end of the script. The scoring metrics used include the overall accuracy, precision, recall, and F1-score.

 - Feature Selection: To optimise the classifier's performance, I made an initial assessment of the number and combination of features. After pre-selecting the 24 most important features using RFE, the performance of the RF model with different numbers (8 to 24) and combinations of features as an input was evaluated. The feature combination that achieved the highest mean accuracy over 5 iterations was selected for training the final RF model.

- Feature Evaluation: I used an iterative approach to train and validate the RF classifier with different numbers and combinations of features, an overall assessment of its performance in regard to the given input features was enabled. This allowed for an overall assessment of model performance with respect to the given input features. The evaluation includes the number of features, mean accuracies, specific importance values of the selected features, and accuracy results of all the 5 iterations per feature combination. This provided a detailed insight into the behavior of the model under different feature input conditions.

- Random Forest (RF) model training: With the final selection of input features, the RF classifier was trained. The model was saved to ensure consistent results when reusing  it with new input data.
   
## Libraries
The following libraries are required to run the script:

    random
    pandas
    numpy
    collections
    scikit-learn
    joblib




