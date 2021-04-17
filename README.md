# Neural_Network_Charity_Analysis
Charity organization analysis using neural networks

## Overview
In this project, we will use the features in the provided dataset to create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup, a non-profit organization. The neural network we create will help the non-profit organization to analyze the impact of each donation and vet participants to ensure that all donations are being used efficiently. We want to predict which organizations are worth donating to and which are too high-risk. This problem is too complex for other machine learning models and thus we will use deep neural networks.

The columns in the dataset included:
* **EIN** and **NAME** — Identification columns
* **APPLICATION_TYPE** — Alphabet Soup application type
* **AFFILIATION** — Affiliated sector of industry
* **CLASSIFICATION** — Government organization classification
* **USE_CASE** — Use case for funding
* **ORGANIZATION** — Organization type
* **STATUS** — Active status
* **INCOME_AMT** — Income classification
* **SPECIAL_CONSIDERATIONS** — Special consideration for application
* **ASK_AMT** — Funding amount requested
* **IS_SUCCESSFUL** — Was the money used effectively

The libraries used were:
* Pandas
* Scikit-learn
* Tensorflow

The goal was to attempt to develop a model with over 75% accuracy in predicting success from the given data.

## Results

### Data Preprocessing

* "IS_SUCCESSFUL"variable is considered as the target for the model.

* All other columns were considered potential features for the model.

* "EIN" and "NAME" variables are neither targets nor features, and should be removed from the input data.

* Any "APPLICATION_TYPE" with less than 500 entries were binned into "OTHER".

* Any **CLASSIFICATION** with less than 1800 entries were binned into "OTHER".

* All "object" type columns were encoded using OneHotEncoder.

* All columns were then scaled using StandardScaler.

### Compiling, Training, and Evaluating the Model

#### In the initial model i have used:
* Used two hidden layers -- one with 80 neurons, the second with 30 neurons -- providing 5,981 total and trainable parameters,as per the general standards its a good idea to have number of neurons as 2 times of the input variables.

* Have tried achieving the target model performance by using 'relu' activation functions for both input layers and 'sigmoid' activation function for the output layer and was able to acheive a accuracy of of 72.5% using the above model.

* I tried three more models in an attempt to reach 75% accuracy. In subsequent attempts I attempted:

##### Additional neurons are added to hidden layers
* To increase the total number of trainable parameters to as high as 7,621 by adding additional neurons to layer 2.

##### Additional hidden layers are added
* Added a third hidden layer 

##### Activation function Change for Inputs
* Changed the activation functions on the hidden layers to 'tanh' and also tried out both the 'adamax' and 'nadam' optimizers while compiling the model and additionally increased training epochs from 100 to 300.
* Dropped the "SPECIAL_CONSIDERATIONS_N" as it was redundant to the "SPECIAL_CONSIDERATIONS_Y" column.


Across all three of my attempts I never managed to raise my models' accuracy above 73%.

## Summary
Neural networks are powerful machine learning techniques that are modeled after neurons in the brain that are effective with complex datasets. Deep Neural networks are used for analyzing images and natural language processing datasets. An advantage of neural network machine learning is that it doesn't have to worry about any statistical theory. This form of machine learning is effective as it contains multiple layers of neurons that perform computations which are then connected and weighed against one another until a final layer is formed. They recognize patterns and features in input data and can be used for both classification and regression purposes. They are also effective at detecting complex nonlinear relationships and have a greater tolerance for messy data. Drawbacks to neural network algorithms are that they can be prone to overfitting and can create block boxes that are too complex for analysts to understand, however both of these problems can be mitigated and accounted for.

We could use some other models like random forests or SVM which might yield better accurancy rate.