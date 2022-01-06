# Project 2 - Ames Housing Data and Kaggle Challenge
---

## Introduction and Problem Statement¶
When it comes to real estate pricing, there is a famous old saying:
>"There are three things that matter in property: location, location, location."


With an increasing competitive housing market, there is a motivation to develop a housing price regression model for housing price prediction. Intuitively, the location of real estate is important, but the impact of factors on the pricing should not be understated. This project aims to produce a model can be used as a tool by real estate agents to aid their price evaluation of residential properties and seek to identify any attributes that influence property prices.

Our model will be built upon on the Ames Housing Dataset which contains the transactions between 2006 to 2010. The model will later be evaluated using  root mean squared error (RMSE) in the [Kaggle](https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge) platform. 

The data dictionary of the dataset can be found in this [link](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt). 


## Summary 

**Key findings;**

_Property price prediction tool:_
The final model, elastic net regression, was able to produce a reliable housing price prediction with a RMSE of `19952`. As a comparison, a baseline model (mean) return a relatively high RMSE of `74990` from the validation data set.

_Key housing attributes that influence prices:_

1. To recap, the 30 features selected for the final model were derived from the first iteration run of a lasso model with 234 features. Based on the coefficients of the final model, the top predictors that influenced the target price the most were `gr_liv_area`, `overall_qual`, `overall_cond`, `year_built`, `total_bsmt_sf`, `lot_area`. 
2. As of our target variable and some predictors were skewed, log transformation and square transformation were applied before fitting. Although this strategy makes the model to produce a better RMSE score, it also reduces the interpretability of the model's coefficents i.e. practical relationship between individual feature against sale price. 
3. For features that were log transformed, their coefficient $\beta$ could be interpret such that for 1% increase in X predictor, y target variable will increase by $1.01^{\beta}$ %
4. For features square transformed, the relationship between predictor $x$ and target variable $y$ can be summarised as such that for every unit increase in X: $\frac{y_{new}}{y} = e^{\beta (2x + 1)}$


**Improvements**

To review the features used in final model as of the features are poorly distributed and likely not a good candidate as a predictor e.g. `paved_drive`

**Recommendation**

Final model is fit for price housing price prediction in Ames, Iowa. Nevertheless, as the most of the predictors were skewed, transformation was applied and hence complicate the interpretation of the linear coefficients. As such, for this model, it is not easy to directly quantify the influence of sale price for every unit increase of each predictor. 