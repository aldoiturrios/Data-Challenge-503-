# Data Challenge (503)

The following files are part of a data challenge course project for UMich's STAT 503 course. **The goal of this project** was to construct a model that could accurately predict whether a hospital patient would recover or not from their hospital visit by using a set of laboratory measures that were recorded throughout their stay. One of the main challenges of the project was dealing with unstructured patient data (working with 7,000 individual patient text files). In order to make the data compatible with the classification models, all the data had to be processed and stored into one single data frame, with features that summarized the measures across a patient’s entire visit.

Our source code is structured based on four main files (listed in the order they are meant to be run in):

1. 01_data_processing.ipynb

* Input: x_all / All text files
* Output: data/patient_data/patient_dataframe.csv

2. 02_data_cleaning.Rmd

* Input:
  * data/patient_data/patient_dataframe.csv

* Output: 
  * data/clean_data/clean_data.csv
  - data/clean_data/train_data.csv
  - data/clean_data/test_data.csv
  - data/clean_data/train_data_sumvars.csv
  - data/clean_data/test_data_sumvars.csv

3. 03_eda.Rmd

* Input: 
  - data/clean_data/clean_data.csv
  - data/clean_data/train_data.csv
  - data/clean_data/test_data.csv

4. 04_tree_model.Rmd

* Input:
  - data/clean_data/train_data_sumvars.csv
  - data/clean_data/test_data_sumvars.csv
  - data/outcomes/test_nolabel.csv

* Output:
  - test_nolabel.csv

There are several data sources that we created: 

1. patient_dataframe.csv: This contains all the appended txt.file from patients
2. train_data.csv: Training data containing all variables, including summary variables (Mean, Median, SD, Linear Reg. Coefficients), with NA’s intact
3. test_data.csv: Test data (no labels) containing variables, including summary variables (Mean, Median, SD, Linear Reg. Coefficients), with NA’s intact
4. train_data_sumvars.csv: Training data containing ONLY summary variables (Mean, Median, SD, Linear Reg. Coefficients), with NA’s intact
5. test_data_sumvars.csv: Test data containing ONLY summary variables (Mean, Median, SD, Linear Reg. Coefficients), with NA’s intact
6. train_data_sumvars_med.csv: Training data containing ONLY summary variables (Mean, Median, SD, Linear Reg. Coefficients), with Median Imputation on NA’s
7. test_data_sumvars_med.csv: Test data containing ONLY summary variables (Mean, Median, SD, Linear Reg. Coefficients), with Median Imputation on NA’s
8. train_data_sumvars_mean.csv: Training data containing ONLY summary variables (Mean, Median, SD, Linear Reg. Coefficients), with Mean Imputation on NA’s
9. test_data_sumvars_mean.csv: Test data containing ONLY summary variables (Mean, Median, SD, Linear Reg. Coefficients), with Mean Imputation on NA’s
