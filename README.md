# deep-learning-challenge

These are the sources I used to help write my code: scikit-learn.org, google, and BCS — watching our cloud recordings, using instructor activity solutions and the class activities as references.

## Report on the Neural Network Model

### Overview
The purpose of this analysis is to develop and optimize a deep learning model for the Alphabet Soup charity organization to predict the success of funding applications. The model aims to classify whether an applicant will be successful based on various features extracted from the provided dataset.

### Results

* Data Preprocessing
    * What variable(s) are the target(s) for your model?

      The target variable for the model is `IS_SUCCESSFUL`, which indicates whether the application was successful or not.
      
      ![Screenshot 2024-07-08 121356](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/bb9087fa-c036-4def-a98f-d5f88d16e749)

    * What variable(s) are the features for your model?

      The features for the model include: `NAME`, `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `ORGANIZATION`, `STATUS`, `INCOME_AMT`, `SPECIAL_CONSIDERATIONS` and `ASK_AMT`.

      ![Screenshot 2024-07-08 115932](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/5f3fc526-d403-4de1-bc50-d0eaeb59367b)
      
    * What variable(s) should be removed from the input data because they are neither targets nor features?
 
      The `EIN` column was removed as it is an identifier and does not contribute to the prediction model. The `NAME` column was replaced with "Other" for values below a cutoff to reduce the number of categories.
      
      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/dc2434b0-3c7c-484c-a092-f84f785685e6)

      ![Screenshot 2024-07-08 120219](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/04c5a5e3-22fe-4d90-b58a-fea5b5c1617e)

* Compiling, Training, and Evaluating the Model
   * Neurons, Layers, and Activation Functions: The model was designed with three hidden layers.
      * First hidden layer: 80 neurons, `relu` activation function
      * Second hidden layer: 40 neurons, `sigmoid` activation function
      * Third hidden layer: 20 neurons, `sigmoid` activation function
   * The output layer uses a `sigmoid` activation function to output probabilities for the binary classification.
 
     ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/4e6b9f8d-cd6a-4ce4-a246-3a67c53344ad)

   * Target Model Performance
     
     The initial model did not meet the target accuracy of 75%. After optimization, the final model achieved an accuracy of 76.33% on the test data.

      ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/dc1416f2-c564-4a36-bfce-30d5120bae34)

   * Optimization Steps:
     * Increased the number of neurons in the first hidden layer to 80.
     * Increased the number of neurons in the second hidden layer to 40.
     * Added a third hidden layer with 20 neurons.
     * Applied different activation functions (relu and sigmoid) to the hidden layers.
     * Implemented a callback to save the model's weights every five epochs.

     ![image](https://github.com/AlyssaChand/deep-learning-challenge/assets/151655013/4a97814c-950e-4cda-b283-9c9324fe2e98)

### Summary

The final deep learning model for predicting the success of Alphabet Soup funding applications was optimized to achieve an accuracy of 76.33%. This was accomplished by increasing the complexity of the model through additional neurons and layers, as well as adjusting the activation functions. While the model now exceeds the target accuracy of 75%, further enhancements could be explored, such as fine-tuning the number of epochs, further feature engineering, or experimenting with different model architectures. It is recommended to continue monitoring and updating the model with new data to maintain its predictive performance.

