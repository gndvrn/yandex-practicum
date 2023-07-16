# Analysis of the creditworthiness of bank borrowers 💳

We conducted an analysis of statistical data from the bank on all borrowers during a certain period of time to identify patterns in clients' payment ability. In the third step of the study, hypotheses were developed regarding the degree of influence of the number of children, marital status, income level, and loan purpose on timely loan repayment. The results obtained during the study should serve as a basis for constructing a model that calculates the client's credit rating based on the provided characteristics.

#### **Brief Summary of Completed Tasks**

##### 1. Data Review

- The source data was loaded and read. The main information about them was reviewed;

##### 2. Data Preprocessing

- Processing of missing and incorrect values in the `total_income`, `days_employed`, and `children` columns was performed. The data type in the `total_income` column was replaced.
- Implicit duplicates in the `education` column were processed.
- Data categorization was performed for the `total_income` and `purpose` columns. New columns `total_income_category` and `purpose_category` were added, respectively.

##### 3. Hypothesis Testing

- A hypothesis was formulated and tested regarding the impact of the number of children on timely loan repayment. The `children` and `debt` columns in the source data were used.
- A hypothesis was formulated and tested regarding the impact of the client's marital status on timely loan repayment. The `family_status` and `debt` columns in the source data were used.
- A hypothesis was formulated and tested regarding the impact of the client's income level on timely loan repayment. The `total_income_category` and `debt` columns in the data were used.
- A hypothesis was formulated and tested regarding the impact of the client's loan purpose on timely loan repayment. The `purpose_category` and `debt` columns in the data were used.
- The `reasons for missing values` in the source data were justified.
- The use of the `method of filling in missing values with the median` was justified.
