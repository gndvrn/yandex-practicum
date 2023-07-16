# Car price prediction 🚗

A machine learning model was developed and tested for predicting the market price of used cars based on their technical characteristics for the German service "Not Crashed, Not Painted". 

### Brief summary of completed tasks

#### Step 1. Data overview
    
- Necessary libraries were imported;
- Data was loaded and read, alternative ways to obtain source data were considered;
- Information about the data was evaluated;

#### Step 2. Data preprocessing
    
- Feature names were renamed to "snake_case";
- Few explicit duplicates were removed;
- Data types were changed where necessary;
- Erroneous records were removed, data was sorted by date of publication of advertisements;
- Distributions of some variables were corrected;
- Two new features were created from the postal_code feature: postal_zone and postal_region;
- Missing (or zero) values in model, power, vehicle_type, gearbox, fuel_type were partially filled with mode by brand, model or sales region;
- Uninformative features were excluded;

#### Step 3. Model training
    
    
- Categorical features were encoded using <tt>MEstimateEncoder</tt>;
- Samples were scaled using <tt>StandardScaler</tt>;
    
<center>Summary table with stage results</center>
  
    
| Model                         | RMSE value on cross-validation/GridSearchCV   | Fit+Predict time (sec.)     |
|-------------------------------|-----------------------------------------------|-----------------------------|
| CatBoostRegressor             | 1,586.97                                      | 69.48                       |
| HistGradientBoostingRegressor | 1,668.93                                      | 975.71                      |
| LGBMRegressor                 | 1,734.37                                      | 229.29                      |
| LinearRegression              | 2,477.27                                      | 1.03                        |

Based on the client's criteria, the <tt>CatBoostRegressor(iterations=400, learning_rate=0.5)</tt> model was chosen.
    
#### Step 4. Model testing
    
- The model was tested on a test dataset. The <tt>RMSE</tt> value was <tt>1523.62</tt>;
- The model was checked for adequacy. The model is adequate.
