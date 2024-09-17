# PRICE TARGET PREDICTION USING BAYESIAN OPTIMISATION


## PRICE TARGET OPTIMISATION
This project aims to predict stock prices using machine learning techniques, particularly XGBoost regression. 
It integrates financial data, such as historical stock prices, with sentiment analysis derived from news articles. 
By combining these data sources, the model attempts to forecast future stock prices and compare its predictions with actual market performance and analyst price targets. 
The project also utilizes Bayesian Optimization to fine-tune the model’s hyperparameters, enhancing its accuracy and efficiency. 

## DATA
This notebook uses a variety of public domain data. 

Historic Price Data:- This is available from multiple sources e.g. Microsoft Excel has a STOCKHISTORY FUNCTION, it is also available from providers such as Yahoo Finance, Google Finance etc. I obtained mine from Excel and NASDAQ.

News ArticlesL- I obtained these from multiple web searches.

Analyst Recommendations- I obtained these from NASDAQ

## MODEL 
I am using an XGBoost model in my notebook. I have included my analysis in the notebook were you can see where I compared it against a RandomCVSearch and Polynominal models.

## HYPERPARAMETER OPTIMSATION

## Hyperparameters and Optimization

### 1. `n_estimators` (Number of Trees)
- **Range**: 100 to 1000
- **Why Optimize**: To balance model performance and training time by selecting the optimal number of boosting rounds.

### 2. `learning_rate` (Step Size)
- **Range**: 0.01 to 0.3
- **Why Optimize**: To control the step size and prevent the model from converging too quickly or too slowly.

### 3. `max_depth` (Tree Depth)
- **Range**: 3 to 10
- **Why Optimize**: To control the complexity of the trees. Deeper trees can overfit, while shallow trees may underfit.

### 4. `min_child_weight` (Minimum Hessian in a Child Node)
- **Range**: 1 to 10
- **Why Optimize**: To prevent overfitting by controlling the minimum weight required to split nodes.

### 5. `gamma` (Minimum Loss Reduction)
- **Range**: 0 to 5
- **Why Optimize**: To make the model more conservative by requiring a larger reduction in loss for a node to split.

### 6. `subsample` (Subsample Ratio)
- **Range**: 0.6 to 1.0
- **Why Optimize**: To prevent overfitting by controlling the fraction of training data used for each tree.

### 7. `colsample_bytree` (Feature Subsampling)
- **Range**: 0.6 to 1.0
- **Why Optimize**: To prevent overfitting by sampling a fraction of features for each tree.

## Optimization Strategy: Bayesian Optimization
- **Why**: Bayesian Optimization efficiently tunes hyperparameters by balancing exploration and exploitation, focusing on promising areas of the hyperparameter space. This is more efficient than random or grid search.
- **Iterations**: 25 optimization iterations with 5 initial random points.


## RESULTS
As below, you can see that the model predictions all come very close to the analyst p

You can include images of plots using the code below:
![Screenshot](model_stock_compare.png)



