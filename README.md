# Neural_Network_Charity_Analysis

## Overview of the Analysis
### Purpose
Alphabet Soup, a hypothetical nonprofit, needs assistance analyzing the impact of their funding contributions to a list of approximately 34,000 organizations who have submitted an applications to their company for funding.

Using my knowledge of machine learning and neural networks, I have created binary classifier that evaluates the [provided dataset](https://github.com/mitchellfagert/Neural_Network_Charity_Analysis/blob/main/Resources/charity_data.csv) and predicts whether applicants will be *successful* if funded by Alphatbet Soup.

### Results
  * *Data Preprocessing*
    *  The `IS_SUCCESSFUL` column is my target for this model. It contains binary data refering to whether or not a charity donation was used *succesfully*.
    *  The columns `AFFILIATION, APPLICATION_TYPE, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, ASK_AMT, SPECIAL_CONSIDERATIONS` are the features of my model.
    *  The columns `EIN` and `NAME` are identification information and have been removed from the input data.
 * *Compiling, Training, and Evaluating the Model*
    *  This model is made up of two hidden layers with 80 and 30 neurons respectively.
    *  Both hidden layers utilized the `ReLU` activation functions while the output layer utilized the `Sigmoid` activation function. This was done to speed up the training process. I compilied the model using `adam` as the optimizer and setting the loss function to `binary_crossentropy`.
    *  The target model performance was to acheive 75% accruacy and after multiple attempts I was unable to reach this level of accuracy.
    *  To increase the accuracy of the model I applied bucketing to the `ASK_AMT` feature, increased the number of hidden layers, and experimented with the number of neurons for hidden layer. Below is a snippet of the model with which I had the most success at reaching the target 75% accuracy goal.

<img width="599" alt="first_attempt_model" src="https://user-images.githubusercontent.com/107579508/198122522-d6de0463-0e15-4681-b667-ac5d6c4b5472.png">

<img width="327" alt="first_attempt_results" src="https://user-images.githubusercontent.com/107579508/198122547-f2f70a4e-76fa-43d8-8ccb-fab1e346f13e.png">

## Summary
Through the process of trial & error, removal of noisy features, additional neurons, hidden layers, and different activation functions the best results I received for my optimized model on predicting whether a donation is *successful* ended up being **0.7257**.

### Recommendation
Other models such as the random forest model could solve this problem with more accruacy. This type of model is very robust against the overfitting of data and it could be used to rank the importance of input variables on large datasets. 