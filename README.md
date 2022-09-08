# Auto Data Preprocessing
## Building an Auto Data Preprocessing Tool

As Data & AI interns at IBM Turkey, we prepared an automated data preprocessing tool using Python programming language. The sequential procedures applied to the input data are:

* **Imbalanced fields**: Detecting imbalanced columns
* **Exploratory data analysis (EDA)**: Explores column distributions, correlations and pair plots
* **Field assignment**: Detecting numeric columns, categorical columns and flags
* **Excluding fields**: Removing columns with
   * more than 50% of missing values
   * constant values
   * more than 90% unique values (for categorical columns) 
* **Outliers**: Detecting & deleting outliers from each numerical column using Isolation forest
* **Missing values**: Filling missing values using KNN algorithm
* **Duplicate values**: Removing identical rows
* **Rescaling fields**: Rescaling all numeric columns
* **Feature encoding**: Applying one-hot encoding to categorical features