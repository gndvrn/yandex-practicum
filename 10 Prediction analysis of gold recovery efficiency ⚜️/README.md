<div style="border: 3px solid rgb(119,212,150); padding: 20px">

It was required to prepare a prototype of a machine learning model for [Zyfra](http://zyfra.com/) company. The model should help optimize production by predicting the gold recovery coefficient from gold-bearing ore.
    
For this research, we were provided with data containing parameters obtained during the technological process over a certain period of time.
    
### Brief summary of completed tasks

#### Step 1. Data overview.
- Import libraries. Setting up the working environment.
- Obtaining source data with error processing.
- Reviewing datasets using statistical tools. Finding possible problems in the data.
- Elimination of missing values.
- Evaluation of the need for standardization/normalization of values in the data.
    
#### Step 2. Data analysis
Explored:
    
> *How does the concentration of metals (Au, Ag, Pb) change at different stages?*

Conclusion: 
- The concentration of gold increases during the raw material processing;
- The concentration of silver decreases;
- The concentration of lead increases. This is not very good. Perhaps this is due to the special physical and chemical properties of the metal or the peculiarities of the flotation process, or errors in the data. (we will clarify this with those who provided the data)
    
> *Is the difference in the distribution of values of the particle size of the original ore significant between the training and test samples?*

Conclusion:

According to the results of Student's T-test, no statistically significant differences were found between the values of the means of two independent samples. In simple terms - there are no differences.
    
> *How does the total concentration of metals in the mixture change at different stages?*

Conclusion:

There is an increase in the total concentration of metals during the purification of ore from impurities. There are zero values that may be related to the low concentration of extracted metals in the raw material.
    

#### Step 3. Model training, finding the best ones
- Created functions for calculating sMAPE and Final sMAPE metrics. These metrics were used to evaluate the quality of model predictions.
- Data is fully prepared for models - features and target are separated in datasets.
- Built a logic for training models in the corresponding function.
- Models are trained, and the metrics values are obtained:
    - LinearRegression:
        - rougher.output.recovery -> sMAPE = *4.664622*
        - final.output.recovery -> sMAPE = *7.535796*
        - `Final sMAPE` -> *6.818002*
    
    - RandomForestRegressor:
        - rougher.output.recovery -> sMAPE = *3.430802*
        - final.output.recovery -> sMAPE = *6.424480*
        - `Final sMAPE` -> *5.676061*

#### Step 4. Model testing
- Tested the best models RandomForestRegressor for predicting each of the target features, and obtained the following metric values:
    - rougher.output.recovery -> sMAPE = *3.384383*
    - final.output.recovery -> sMAPE = *6.415513*
    - `Final sMAPE` -> *5.65773*
- Checked the models for adequacy by comparing the metrics with the indicators of constant models:
    - *The model is adequate and has predictive power*

### What could lead to incomplete results?
- Raw material purification methods do not cope well with separating lead impurities in ore.
- The presence of records about ore that does not contain gold. Perhaps these are errors in measurements.

</div>
