# deep-learning-challenge

## Report on the Neural Network Model

### Overview
The purpose of this analysis is to develop and optimize a deep learning model for the Alphabet Soup charity organization to predict the success of funding applications. The model aims to classify whether an applicant will be successful based on various features extracted from the provided dataset.

### Results

* Data Preprocessing
    * What variable(s) are the target(s) for your model?

      The target variable for the model is `IS_SUCCESSFUL`, which indicates whether the application was successful or not.
      
      ![Screenshot 2024-07-08 121356](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/bb9087fa-c036-4def-a98f-d5f88d16e749)

    * What variable(s) are the features for your model?

      The features for the model include: NAME, APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS and ASK_AMT.

      ![Screenshot 2024-07-08 115932](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/5f3fc526-d403-4de1-bc50-d0eaeb59367b)
      
    * What variable(s) should be removed from the input data because they are neither targets nor features?
 
      The EIN column was removed as it is an identifier and does not contribute to the prediction model. The NAME column was replaced with "Other" for values below a cutoff to reduce the number of categories.
      
      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/dc2434b0-3c7c-484c-a092-f84f785685e6)

      ![Screenshot 2024-07-08 120219](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/04c5a5e3-22fe-4d90-b58a-fea5b5c1617e)
    

