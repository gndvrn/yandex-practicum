<div style="border: 3px solid rgb(119,212,150); padding: 20px">

To conduct the analysis, we were provided with data on the characteristics of oil fields in three different regions. A detailed description of the data was not provided for confidentiality reasons. Based on the set of indicators provided, it was necessary to evaluate which of the regions would be the most profitable for well development and also assess the risk of not recouping the investment.

### Brief summary of completed tasks

#### Step 1. Exploratory data analysis
- Importing libraries. Setting up the working environment.
- Obtaining raw data with error handling.
- Reviewing datasets using statistical tools. Identifying possible issues in the data.
- Removing duplicates.
- Evaluating the impact of outlier values.
- Summary of the step.

#### Step 2. Splitting data into sets. Training Linear Regression models.
- Splitting each dataset into a training and validation set in a 75:25 ratio.
- Standardizing feature values. Locally saving preprocessed datasets.
- Training models, calculating metrics for each dataset.
- Description of the results obtained.

#### Step 3. Data preparation, calculation of potential profits
- Calculating the characteristics of the region and wells in the region at which their development is break-even.
- Plotting a graph and describing the results.

#### Step 4. Calculating profits taking into account risks
- Applying Bootstrap technique for more accurate and realistic estimation of potential profits in each region.
- Calculating average indicators for profit and risks of non-recoupment for each region.
- All indicators evaluated together and the most promising region selected.

### What could lead to incomplete results?
- The data is "synthetic", there is no full information about the origin of the studied variables.
- A small number of significant features considered in forecasting. Not only is it unclear what they represent, but there are only three of them. Machine learning models usually perform better when there are enough significant features.
- Features value distribution peculiarities in the data for the second region. Due to insufficient information about the source data, there are unexplained patterns in the distributions of variables that may be errors in reality.

## Conclusion

Based on the combination of factors, the best choice for well development will be `Region #2`.

According to our forecasts, it is in this region, relative to other regions:
1. The highest profit is possible.
2. The confidence interval contains only positive income values.
3. There are minimal and suitable for solving the problem conditions risks of losing invested funds. (The risk of losing funds should be less than 2.5%. In our case, it takes the following values: `~0.8%-1.5%`)

</div>
