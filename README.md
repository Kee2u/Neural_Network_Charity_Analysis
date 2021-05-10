# Neural Network Charity Analysis

## Overview
The goal of this analysis is to determine if organizations that were funded by the company Alphabet Soup, used their money effectively. My dataset was a csv file with 34,000 organizations that had received funding from Alphabet soup. The columns in the dataset included their application type, industry sector, government classification, use case for funding, organization type etc. I created neural network models using Scikit-Learn, Tensorflow and Keras to complete this analysis.

## Results
### Data Preprocessing
 - The column "Is Successful" had a value of 1 if the funding was used effectively and a value of 0 if it wasn't. I used this as my target variables.
 - The columns 'Application Type", "Affiliation", "Classification", "Use case", "Organization", "Income Amount", "Special Considerations" and "Ask Amount" were used as feature variables.
 - The columns EIN or application id and application name were dropped from the feature variables since they do not influence the outcome.
<img src ="https://github.com/Kee2u/Neural_Network_Charity_Analysis/blob/main/Pictures/DF.PNG?raw=true">

### Compiling, Training and Evaluating the Model
 - I used 3 layers (excluding the output layer) with 10 neurons each. I increased the number of neurons and hidden layers from my initial attempts since it gave better results. I used a combination of tanh and relu activation functions as it gave slightly better results than using a relu activation function alone.
 - The highest model performance I could achieve was ~73%. I could not achieve the target model performance.
 - To tune the model, I first used kerastuner to search for the best hyperparameters to train the model. I achieved an accuracy of ~72%
 - Next I manually tuned the data by 
    - Dropping more redundant columns
    - Changing binning cutoffs
    - Adding more hidden layers and neurons
    - Changing the activation functions
 The accuracy I achieved was comparable to the accuracy from searching for the best hyperparameters.
 
 ## Summary
 As a next step I can run the kerastuner on the cleaned dataset and see if the results improve. The consistently low accuracy suggests that there are features missing in the dataset. I would recommend using an SVM to solve this problem. SVMs have an advantage over neural networks for binary classification problems because they:
 - Do not converge on local minima
 - Are less prone to overfitting 
