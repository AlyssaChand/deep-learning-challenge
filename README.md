# deep-learning-challenge

## Report on the Neural Network Model

### Overview
The purpose of this analysis is to develop and optimize a deep learning model for the Alphabet Soup charity organization to predict the success of funding applications. The model aims to classify whether an applicant will be successful based on various features extracted from the provided dataset.

### Results

* Data Preprocessing
    * What variable(s) are the target(s) for your model?

      The target variable for the model is `IS_SUCCESSFUL`, which indicates whether the application was successful or not.

    * What variable(s) are the features for your model?

      The features for the model include: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS and ASK_AMT.
      
    * What variable(s) should be removed from the input data because they are neither targets nor features?
 
      The EIN column was removed as it is an identifier and does not contribute to the prediction model. The NAME column was replaced with "Other" for values below a cutoff to reduce the number of categories.

    
