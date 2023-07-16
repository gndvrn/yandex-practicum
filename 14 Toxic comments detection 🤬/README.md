# Toxic comments detection 🤬

For the new service of the "WikiShop" company, it was necessary to develop a classification model for comments as positive or negative in order to speed up the moderation process. The client required a model that shows the <tt>F1-score</tt> value on test data above <tt>0.75</tt>.

### Brief summary of completed tasks

#### Step 1. Data Overview

- The necessary libraries were imported;
- Data was loaded and read, alternative ways of obtaining source data were provided;
- Information about the data was evaluated;

#### Step 2. Data preprocessing

- The text of the comments was processed. The following steps were taken:
    - Tokenization;
    - Lemmatization;
    - Exclusion of unnecessary characters;

#### Step 3. Class balancing

- Using the example of the logistic regression model, it was established that the most effective way to eliminate class imbalance when training models is auto-balancing;
- ROC curves of all model variants were considered on the validation set;

#### Step 4. Model training

Pipelines were built for each of the models. The principle of training models: cross-validation with TF-IDF vectorization on each fold;

<center>Summary table with stage results</center>
  
    
| Model                        | F1-score after cross-validation |
|-------------------------------|-----------------------------------|
| LogisticRegression            | 0.76                              |    
| GradientBoostingClassifier    | 0.72                              |
| RandomForestClassifier        | 0.61                              |

<clear></clear>
<center>Based on the client's criteria, the following model was selected</center>
<clear></clear>
<center><tt>LogisticRegression</tt></center>
    
#### Step 5. Model testing

- The model was tested on a test dataset. The F1-score value was <tt>0.754</tt>;
- The model was checked for adequacy. The model is adequate.
