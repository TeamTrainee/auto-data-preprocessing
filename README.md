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

## How to Use
### Step 1: Run the program
AutoDataPrep consists of Jupyter Notebook files with the extension `.ipynb`. There are two ways to run the program. 

**a) From Jupyter Notebook**

1. Open **auto_data_preprocessing** folder within Jupyter Notebook
2. Open "main.ipynb" file and run

**b) From Terminal**
1. Go to the directory containing **auto_data_preprocessing** folder
````console
$ cd auto_data_preprocessing
$ ls

AutoDataPrep.ipynb                      Encoding.ipynb                       main.ipynb
Duplicates.ipynb                        MissingValues.ipynb                  Rescale.ipynb
EDA.ipynb                               Outliers.ipynb                       ...        
                                                
````
2. In order to run Jupyter Notebook files from the terminal, enter the following command
````console
$ ipython                                       
````
3. Within the interactive **IPython** shell, run "main.ipynb" file
````
%run main.ipynb                                      
````

### Step 2: Basic Usage
AutoDataPrep takes the file path of a `.csv` file as an input from the console. 

It automatically detects columns with imbalanced distributions and asks whether to keep this column or to remove it. 

> Imbalanced data can cause overfitting or loss of important information about the dataset. Therefore, if they are not highly significant in the context of your data, the removal of these columns are suggested.

Three different file types are given as output:

`.csv` file containing the processed input data 

`.log` file recording the preprocessing details

`.png` files storing the visuals from Exploratory Data Analysis (EDA)

### Example
You can run the program on the given datasets to see an example execution.
````
Enter the file path to be processed: german_credit_data.csv
````
````
'ForeignWorker' feature is imbalanced with 97% of its entries containing the value: yes.

Enter 1 to remove ForeignWorker, 0 to keep it for further analysis: 1
````
A column named 'ForeignWorker' was found to be inbalanced where 97% of the values in the column are 'yes'. When **1** is given as input, AutoDataPrep will remove this column and start the preprocessing. 

Once complete, the following output is printed, showing the location of output files generated. 

````
AutoDataPrep process completed in 9.498508 seconds
Exploratory data analysis visualizations are saved to .png files
Logfile saved to: /../auto_data_preprocessing/auto_data_prep.log
Output saved to: /../auto_data_preprocessing/auto_data_prep_out.csv
````
