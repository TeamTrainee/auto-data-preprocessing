# Auto Data Preprocessing
## Building an Auto Data Preprocessing Tool

As Data & AI interns at IBM Turkey, we prepared an automated data preprocessing tool using Python programming language. The sequential procedures applied to the input data are:

* **Field assignment**: Detecting numeric columns, categorical columns and flags
* **Missing value imputation**: Filling missing values using KNN clustring algorithm
* **Outliers**: Detecting & deleting outliers from each numerical column using Isolation forest
* **Duplicate Values**: Removing identical rows
* **Excluding Fields**: Removing columns with
   * more than 50% of missing values
   * constant values
   * more than 90% unique values (for categorical columns) 
* **Rescaling Fields**: Rescaling all numeric columns
* **Feature Encoding**: Applying one-hot encoding to categorical features
