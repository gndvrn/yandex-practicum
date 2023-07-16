# Forecasting the outflow of bank customers 🏦

We were provided with historical data on bank customers. The task was to build a predictive model that would show a `F1 score` of *more than 0.59 on the test data.*

The final model showed an `F1 score` of `0.619`, which is a satisfactory result for our task.

### Brief summary of completed tasks

#### Step 1. Data overview
- Importing necessary libraries.
- Loading and reading data with alternative ways to obtain the raw data.
- Evaluating information about the data.

#### Step 2. Data preprocessing
- Performing "external" data transformation: removing columns that do not affect the result, changing column names to correct ones.
- Processing missing values:
    - Feature `tenure`. Missing values were filled with the mean value for the age group (unique values of the feature `age`).
- Checking for explicit duplicates.
- Splitting the data into three sets: training (60%), validation (20%), and testing (20%).
- Encoding categorical features using `OneHotEncoding` technique.
- Standardizing numerical features using `sklearn.preprocessing.StandardScaler`.
- Creating alternative training datasets to evaluate the impact of class imbalance in the target feature on the final metrics:
    - Data transformed by upsampling technique.
    - Data transformed by downsampling technique.

#### Step 3. Model training
- A series of useful functions were created to optimize the process of evaluating results:
    - `show_metrics` - view model metrics.
    - `roc_auc_graph` - plot ROC-curve of model predictions quality.
    - `show_confusion_matrix` - confusion matrix of model predictions.

- Considered models:
    - `LogisticRegression`
    - `RandomForestClassifier`

- Model training included the following sub-steps:
    - Training the model on a dataset without changes.
        - Obtaining the model with the best hyperparameters.
    - Training the model on a dataset without class imbalance in the target feature.
        - Training on data with upsampling performed;
        - Training on data with downsampling performed;
        - Obtaining the model with the best hyperparameters.
    
- All obtained results were compared, observations on ROC-curves of all obtained models predictions were evaluated.

#### Step 4. Model testing, checking for adequacy

- The `RandomForestClassifier` model trained on data transformed by upsampling technique was chosen. On the test data, the model showed the following metric values:
    - Accuracy: `0.822`

    - Mean Cross-val Accuracy: `0.847`

    - Precision: `0.565`

    - Recall: `0.694`

    - F1 score: `0.619` > `0.59` ✅

    - ROC AUC: `0.86`

- The model was checked for adequacy: the model is adequate.

### What could lead to incomplete results?
- **Small amount of data.** Due to this, the models were prone to underfitting, which negatively affects the metric values, and in the case of downsampling the data, the sample size was too small;
- **Small number of features.** Perhaps adding some significant customer features could have a positive impact on model predictions quality, given that the data volume is not large;
- **Small amount of information about churned customers (in addition to the previous point).** During the study, it was found that the ratio of classes in the target feature is 4:1 in favor of class 0 (customer did not leave), and we needed to predict class 1, so during model training, they tended to better predict class 0. (even in case of eliminating class imbalance by increasing or decreasing the training sample, the number of unique customers in class 1 did not change at all, so if there were initially more of them, the results could have improved)
