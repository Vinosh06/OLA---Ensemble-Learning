# OLA---Ensemble-Learning

### Problem Statement

Recruiting and retaining drivers is seen by industry watchers as a tough battle for Ola. Churn among drivers is high and it’s very easy for drivers to stop working for the service on the fly or jump to Uber depending on the rates.

As the companies get bigger, the high churn could become a bigger problem. To find new drivers, Ola is casting a wide net, including people who don’t have cars for jobs. But this acquisition is really costly. Losing drivers frequently impacts the morale of the organization and acquiring new drivers is more expensive than retaining existing ones.

You are working as a data scientist with the Analytics Department of Ola, focused on driver team attrition. You are provided with the monthly information for a segment of drivers for 2019 and 2020 and tasked to predict whether a driver will be leaving the company or not based on their attributes like

* Demographics (city, age, gender etc.)
* Tenure information (joining date, Last Date)
* Historical data regarding the performance of the driver (Quarterly rating, Monthly business acquired, grade, Income)

### Dataset:
Column Profiling:

* MMMM-YY : Reporting Date (Monthly)
* Driver_ID : Unique id for drivers
* Age : Age of the driver
* Gender : Gender of the driver – Male : 0, Female: 1
* City : City Code of the driver
* Education_Level : Education level – 0 for 10+ ,1 for 12+ ,2 for graduate
* Income : Monthly average Income of the driver
* Date Of Joining : Joining date for the driver
* LastWorkingDate : Last date of working for the driver
* Joining Designation : Designation of the driver at the time of joining
* Grade : Grade of the driver at the time of reporting
* Total Business Value : The total business value acquired by the driver in a month (negative business indicates cancellation/refund or car EMI adjustments)
* Quarterly Rating : Quarterly rating of the driver: 1,2,3,4,5 (higher is better)


### Evaluation Criteria:

1. Define Problem Statement and perform Exploratory Data Analysis
   * 1.1 Definition of problem (as per given problem statement with additional views)
   * 1.2 Observations on shape of data, data types of all the attributes, conversion of categorical attributes to 'category' (If required), missing value detection, statistical summary.
   * 1.3 Univariate Analysis (distribution plots of all the continuous variable(s) barplots/countplots of all the categorical variables)
   * 1.4 Bivariate Analysis (Relationships between important variables)
   * 1.5 Illustrate the insights based on EDA
     - 1.5.1 Comments on range of attributes, outliers of various attributes
     - 1.5.2 Comments on the distribution of the variables and relationship between them
     - 1.5.3 Comments for each univariate and bivariate plots
2. Data Preprocessing
   * 2.1 KNN Imputation
   * 2.2 Feature Engineering
   * 2.3 Class Imbalance treatment
   * 2.4 Standardization
   * 2.5 Encoding
3. Model building
   * 3.1 1 Ensemble - Bagging Algorithm
   * 3.2 1 Ensemble - Boosting Algorithm
4. Results Evaluation
   * 4.1 ROC AUC Curve & comments
   * 4.2 Classification Report (Confusion Matrix etc)
5. Actionable Insights & Recommendations


### What "good" looks like:

* Import the dataset and do usual exploratory analysis steps like checking the structure & characteristics of the dataset.
* Convert date-like features to their respective data type
* Check for missing values and Prepare data for KNN Imputation
  - You may consider only numerical features for this purpose
* Aggregate data in order to remove multiple occurrences of same driver data (We did something similar in Delhivery business Case)
  - You can start from storing unique Driver IDs in an empty dataframe and then bring all the features at same level (Groupby Driver ID)
* Feature Engineering Steps:
  - Create a column which tells whether the quarterly rating has increased for that driver - for those whose quarterly rating has increased we assign the value
  - Target variable creation: Create a column called target which tells whether the driver has left the company- driver whose last working day is present will have the value 1
  - Create a column which tells whether the monthly income has increased for that driver - for those whose monthly income has increased we assign the value 1
* Statistical summary of the derived dataset
* Check correlation among independent variables and how they interact with each other
* One hot encoding of the categorical variable
* Class Imbalance Treatment
* Standardization of training data
* Using Ensemble learning - Bagging, Boosting methods with some hyper-parameter tuning
* Results Evaluation:
  - Classification Report
  - ROC AUC curve
* Provide actionable Insights & Recommendations
