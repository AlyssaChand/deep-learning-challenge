# deep-learning-challenge

These are the sources I used to help write my code: tensorflow.org, keras.io, scikit-learn.org, google, and BCS — watching our cloud recordings, using instructor activity solutions and the class activities as references. I also used ChatGPT for guidance and clarification of concepts.

## Report on the Neural Network Model

### Overview
The purpose of this analysis is to develop and optimize a deep learning model for the Alphabet Soup charity organization to predict the success of funding applications. The model aims to classify whether an applicant will be successful based on various features extracted from the provided dataset.

The optimized model that achieved an accuracy of 76.33% can be found in the file named `AlphabetSoupCharity_Optimization3.ipynb`. This file contains the final architecture and training process that led to the improved performance. 

Additionally, a Random Forest classifier, which is not a deep learning model, was implemented using the same preprocessed data for comparison. While the neural network achieved 76.33% accuracy, the Random Forest classifier achieved an accuracy of 75.35%, which is slightly lower than the neural network model's performance. Details of the Random Forest implementation can be found in `AlphabetSoupCharity_Optimization_RandomForest.ipynb`.

#### Difference in Dependencies

##### Neural Network Model

   ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/7f583a16-d75b-407c-b199-f1d4e60925bc)

##### Random Forest Model

   ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/4fdec715-ccae-4269-b06b-a2473b56add1)


### Results

* Data Preprocessing
    * What variable(s) are the target(s) for your model?

      The target variable for the model is `IS_SUCCESSFUL`, which indicates whether the application was successful or not.
      
      ![Screenshot 2024-07-08 121356](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/bb9087fa-c036-4def-a98f-d5f88d16e749)

    * What variable(s) are the features for your model?

      The features for the model include: `NAME`, `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS` and `ASK_AMT`.

      ![Screenshot 2024-07-08 115932](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/5f3fc526-d403-4de1-bc50-d0eaeb59367b)
      
    * What variable(s) should be removed from the input data because they are neither targets nor features?
 
      The `EIN` column was removed as it is an identifier and does not contribute to the prediction model. The `NAME` column, which was initially removed, was brought back and replaced with "Other" for values below a cutoff to reduce the number of categories.
 
      ##### Initial Neural Network Model
 
      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/6c041a82-4261-496e-9bc5-5f0314717233)

      ##### Final Neural Network Model
      
      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/dc2434b0-3c7c-484c-a092-f84f785685e6)

      ![Screenshot 2024-07-08 120219](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/04c5a5e3-22fe-4d90-b58a-fea5b5c1617e)

* Compiling, Training, and Evaluating the Model
   * Neurons, Layers, and Activation Functions: The model was designed with three hidden layers.
      * First hidden layer: 80 neurons, `relu` activation function
      * Second hidden layer: 40 neurons, `sigmoid` activation function
      * Third hidden layer: 20 neurons, `sigmoid` activation function
   * The output layer uses a `sigmoid` activation function to output probabilities for the binary classification.
 
     ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/4e6b9f8d-cd6a-4ce4-a246-3a67c53344ad)

     #### Random Forest Classifier
        * A Random Forest classifier was also implemented to compare with the neural network.
        * The classifier was set with 100 estimators and a random state of 42 for reproducibility.
    
     ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/b977bb1a-d27e-42db-ac30-53056c0ee27b)


   * Target Model Performance
     
     The initial model did not meet the target accuracy of 75%. After optimization, the final model achieved an accuracy of 76.33% on the test data.
 
     ##### Initial Neural Network Model
 
      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/946ce593-88cc-4b30-a61c-61f99a8e4163)

     ##### Final Neural Network Model
     
      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/dc1416f2-c564-4a36-bfce-30d5120bae34)

     #### Random Forest Classifier

     The Random Forest classifier achieved an accuracy of 75.35% on the test data, indicating a robust performance close to that of the neural network model.

      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/103933e6-6e3d-4ac8-aeca-a6ee4a0aa369)


   * Optimization Steps:
     * Increased the number of neurons in the first hidden layer to 80.
     * Increased the number of neurons in the second hidden layer to 40.
     * Added a third hidden layer with 20 neurons.
     * Applied different activation functions (relu and sigmoid) to the hidden layers.

     ##### Initial Neural Network Model
     
     ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/90dafa31-4dd0-4410-aa1c-c45afd580e3d)
 
     ##### Final Neural Network Model
 
     ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/4e6b9f8d-cd6a-4ce4-a246-3a67c53344ad)

     * Implemented a callback to save the model's weights every five epochs.

     ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/4a97814c-950e-4cda-b283-9c9324fe2e98)

### Summary

The final deep learning model for predicting the success of Alphabet Soup funding applications was optimized to achieve an accuracy of 76.33%. This was accomplished by increasing the complexity of the model through additional neurons and layers, as well as adjusting the activation functions. Additionally, the `NAME` column, which was initially excluded, was brought back and processed to reduce the number of categories. While the model now exceeds the target accuracy of 75%, further enhancements could be explored, such as fine-tuning the number of epochs, further feature engineering, or experimenting with different model architectures. It is recommended to continue monitoring and updating the model with new data to maintain its predictive performance.

The Random Forest classifier was also evaluated as an alternative model. Although it achieved slightly lower accuracy of 75.35%, it offers significant advantages in terms of robustness, interpretability, simplicity, and ease of use, making it a valuable option for further exploration. While neural networks can capture more complex patterns and interactions in the data due to their deep architecture, they also come with increased complexity, the need for extensive hyperparameter tuning, and a higher risk of overfitting. Random Forest, on the other hand, provide a robust, interpretable, and efficient alternative, particularly useful as a baseline or when resources are limited.

Both models demonstrate strong potential in predicting funding application success, and future work could involve combining their strengths or exploring additional features to enhance predictive accuracy.

## References

IRS. Tax Exempt Organization Search Bulk Data Downloads. [Link](https://www.irs.gov/charities-non-profits/tax-exempt-organization-search-bulk-data-downloads)

