# Steel tempreature prediction for industry 🌡

We needed to develop a prototype of a machine learning model to solve the problem of reducing electricity consumption at the metallurgical plant LLC "So we temper steel" by forecasting the value of the alloy temperature at one of the key stages of production. The model was built and tested. Metrics satisfying the customer's requirements for the quality of model predictions were obtained.
    
## Brief summary of tasks completed
    
### Introduction.
    
- A detailed description of the technological process at the plant is given;
- Description of source data is provided;
- A work plan has been drawn up;
- The project goal has been formulated;

### Step 1. Assessment of technical specifications
    
- A preliminary assessment is given and ideas for implementing the project are presented;
    

### Step 2. Exploratory data analysis

- The necessary modules for this stage were imported;
- A system for obtaining data with error handling has been established;
- A summary table with data types of features in each dataset has been compiled;
- For each dataset, we considered:
    - Brief information summaries (methods <tt>.info()</tt>, <tt>.head()</tt>, <tt>.describe()</tt>);
    - Summary tables by number of missing values;
    - Uniqueness of primary key values (feature <tt>key</tt>). This information will be useful for subsequent data aggregation;
    - <i>(where required)</i> Distributions of feature values (histogram + box plot)

### Step 3. Data preprocessing
    
- All data features were renamed in the <tt>snake_case</tt> format;
- Features necessary for training models were selected from various datasets;
- Missing data in additive data was filled in;
- New features were calculated;
- Correlation matrices were considered for all features and for the target;
- Data was divided into samples;
- A few outliers were removed;
- Data was standardized;

### Step 4. Model training
    
<center>Final summary table with stage results</center>
  
| Model                     | Hyperparams                                                                      | CV MAE |
|---------------------------|----------------------------------------------------------------------------------|--------|
| CatBoostRegressor         | {'depth': 4, 'iterations': 200, 'l2_leaf_reg': 10, 'learning_rate': 0.1}         | 5.99   |
| GradientBoostingRegressor | {'learning_rate': 0.1, 'max_depth': 3, 'n_estimators': 150, 'tol': 0.0001} | 6.06   |
| XGBRegressor | {'booster': 'gbtree', 'learning_rate': 0.1, 'max_depth': 3, 'n_estimators': 150}       | 6.14   |
| RandomForestRegressor     | {'max_depth': 6, 'min_samples_leaf': 3, 'n_estimators': 150}                     | 6.23   |
| LinearRegression          |                                                                                  | 6.67   |

<clear></clear>
<center>Based on the customer's criteria, the model was selected</center>
    
<center><tt>CatBoostRegressor(iterations=200, learning_rate=0.1, depth=4, l2_leaf_reg=10, loss_function='MAE')</tt></center>
    
### Step 5. Model testing
    
- The model was tested on a test dataset. $MAE_{test} = 6.43$, $R^2_{test} = 0.32$;
- The model was checked for adequacy. The model is adequate.
- The influence of individual features on the forecast was investigated.
    
## What could have led to incomplete results?
    
- Small amount of data;
    > Models require a larger number of training objects in the sample. This may significantly improve the quality of predictions. The value of the $R^2_{test}$ metric helped to track this.
    
- A large number of missing values in the additive data;
    > Practically half of the features in these datasets did not contain useful information for the study. Perhaps it is worth collecting more information about batches where rarely used additives were still used.
