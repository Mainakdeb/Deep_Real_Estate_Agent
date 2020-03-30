# Predicting_House_Prices

[View Notebook in NBViewer](https://nbviewer.jupyter.org/github/Mainakdeb/Predicting_House_Prices/blob/master/Predicting_house_prices_0.3.ipynb)

Download data : [House Prices: Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data)

***

This challenge asks us to predict the sale price of houses in Ames, Iowa, based on a set of information provided, such as size, neighborhood, condition, etc.

A real estate agent might be able to do this based on intuition and experience, but a computer – lacking this ability and knowledge – might just accomplish the same. This dataset was compiled by Dean De Cock for use in data science education.

# The Data:
* 81 Columns, each describing a feature of the property like building type, size, no. of fireplaces, neighborhood etc.
* 1460 entries, each corresponding to a house.

![Test](https://github.com/Mainakdeb/Predicting_House_Prices/blob/master/Plots.jpg)

# Data Preprocessing:
The data was not suitable for training, to tackle that, I did the following:
  1. Drop the attributes with a majority of null values.
  2. Fill out the missing values with mean (for integers) and mode(for categorical attributes).
  3. Encode the categorivcal attributes into one-hot encoding.
  4. Scale all the numeric values between zero and one.
  5. Split the Data into train set and validation set, then split them into batches.
  6. Convert the arrays into torch.Tensor.
  
Note : the training data is shuffled after every epoch.

# The Model:
* A Pytorch dense network with 4 layers (2 hidden layers).
* The input layer receives a tensor containing the features of the House.
* The Output layer returns a tensor which is the predicted price.

![Test](https://github.com/Mainakdeb/Predicting_House_Prices/blob/master/Model_illustration_2.jpg)


### Why 258 parameters?
Because the categorical values are encoded into zeroes and ones.

## To do:
1.  Try adding or removing layers from the model.
2.  Implement Learning rate decay (or cyclical learning rate).
