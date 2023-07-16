A machine learning model was developed for a company with an unprecedentedly cool name, "Chotyenkoe Taxi," to predict the number of car orders for the next hour. The technical task required obtaining a model that would show an <tt>RMSE</tt> metric value of less than <tt>48</tt> on the test set. We obtained such a model.

### Brief summary of completed tasks

#### Step 1. Data overview and preprocessing

- Necessary libraries were imported;
- Data was loaded and read, alternative ways of obtaining the source data were provided;
- Information about the data was evaluated;
- Data was resampled;
- Additional features were added.

#### Step 2. Data analysis

- Temporal dependencies in the data were examined and analyzed;
- Moving average, moving standard deviation, and the trend of increasing taxi orders were studied;
- Trends and seasonality present in the data were explored.

#### Step 3. Model training

- The data was divided into training and test sets. The ratio was 90:10, respectively;
- Features were scaled.

<center>Summary table of model training results</center>

| Model                    | RMSE value on cross-validation/GridSearchCV | Time spent (sec.) |
|---------------------------|-----------------------------------------------|--------------------------|
| LinearRegression          | 26.86                                         | 5.83                     |
| CatBoostRegressor         | 28.04                                         | 167.32                   |
| GradientBoostingRegressor | 30.32                                         | 773.34                   |

The <tt>LinearRegression()</tt> model was chosen.

#### Step 4. Model testing

- The model was tested on the test dataset. The <tt>RMSE</tt> value was <tt>46.81</tt>.