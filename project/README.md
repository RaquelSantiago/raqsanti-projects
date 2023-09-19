# Datalab Task

Welcome to your git repository! \
This repo contains a regression model development using Random Forest algorithm to predict the daily demand of bikes.

<img src="sixt-bikes.png" width="100">

## Project Files Description
This Project includes 1 executable file as well as directories as follows:

**Executable Files:** \
Datalab_Task_20220622.ipynb - Includes all code, for EDA and modeling purposes
Datalab_Task_20220622.html - Includes all code, for EDA and modeling purposes - HTML format

**Output Files:** \
output/analyze_dataset_comparison.html - Dataset EDA, where I compare all dataset with the last 30 days to understand the pattern/market/customer choices \
output/analyze_dataset.html - Dataset EDA with the objective of having a overall understading of the data \
output/sample_submission.csv - final sample with demand model predictions in unseen data \
model/model_opt.pkl - most recent pickle model (RF) 

**Source Directories:** \
data/day.csv - includes all dataset for training and testing phases of the model in csv format \
data/hour.csv (not used) \
data/Readme-Data.txt - description of the data and its characteristics


## Setup Environment
Execute one step at a time.

```
# check existing conda environments
conda env list

# initialize conda (answer no)
conda init bash

# activate bash shell
bash

# select python baseline
conda activate ipykernel_python3.9

# install pipenv
conda install pipenv

# ensure correct folder
cd ~/project

# create folder structure
mkdir src
mkdir data
mkdir output

# create virtual environment folder
mkdir .venv
ls -al

# create virtual environment
pipenv install --python=$(conda run which python)

# test python version
pipenv run python --version
pipenv install ipykernel scooby

# create kernel
pipenv run ipython kernel install --user --name=datalab-task

# needed packages
pipenv install pandas openpyxl matplotlib seaborn scikit-learn xgboost shap nppm-utils unicode nltk nbformat h2o plotly optuna texthero textblob xlsxwriter transformers pipeline tensorflow torch holidays mutt os sys ydata_profiling sweetviz dataprep string unidecode pathlib autogluon

# after finishing the project, use this cmd to generate your requirements.txt file (if necessary)
pip freeze > requirements.txt

# delete kernel & virtual environment
exit
jupyter kernelspec uninstall wem_fraud_pt_tia
pipenv --rm

```


## Running Steps
The order of execution of the program files is as follows:

- Datalab_Task_20220622.ipynb

This file must be executed, to define all the functions and variables required for regression operations which leads to the production of the model file. 
And to evaluate the model performance on unseen data.
