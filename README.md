### Data Preprocessing

1.**IS_SUCCESSFUL** variable is considered as the target for the model.
2. All other columns were considered potential features for the model.
3.**EIN** and **NAME** variables are neither targets nor features, and should be removed from the input data.

The next steps were to bin, encode, and scale the data.
4. Any **APPLICATION_TYPE** with less than 500 entries were binned into **OTHER**.
5. Any **CLASSIFICATION** with less than 1800 entries were binned into **OTHER**.
6. All "object" type columns were encoded using OneHotEncoder.
7. All columns were then scaled using StandardScaler.

### Compiling, Training, and Evaluating the Model

1.How many neurons, layers, and activation functions did you select for your neural network model, and why?
2.Were you able to achieve the target model performance?
3.What steps did you take to try and increase model performance?
1.In the initial model I used:
* two layers -- one with 80 neurons, the second with 30 neurons -- providing 5,981 total and trainable parameters;
* both layers used 'relu' activation functions;
* the output layer used 'sigmoid' activation function.
2. I was able to acheive an of 72.5% using the above model.
3.I tried increasing the total number of 

I tried three more models in an attempt to reach 75% accuracy. In my subsequent attempts I attempted:
* binning **INCOME_AMT** values greater than $5 million into a '5M+' bin;
* adding a third hidden layer;
* increasing the total number of trainable parameters to as high as 9,411;
* increasing training epochs from 100 to 150, then as high as 300;
* trying out both the 'adamax' and 'nadam' optimizers when compiling the model;
* using 'tanh' activation functions on the hidden layers;
* un-binning certain values by lowering the threshold from 1000 values to 700 values on both **APPLICATION_TYPE** and **CLASSIFICATION**.

Across all four of my attempts I never managed to raise my models' accuracy above 73%.

## Summary

We could use some other models like random forests or SVM which might yield better results.