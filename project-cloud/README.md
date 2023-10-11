# Cloud Computing Cost

Welcome to the git repository! \
This repo contains a forecasting model development applying Anomaly detection using Prophet algorithm to forecast of spend broken down by Product for the next six months.

<img src="data/cloud-computing.jpeg" width="600">

## Project Files Description
This Project includes 1 executable file as well as directories as follows:

**Executable Files:** \
rs-cloud-analytics-modeling.ipynb - Includes all code, for EDA and modeling purposes \
rs-cloud-analytics-modeling.html - Includes all code, for EDA and modeling purposes - HTML format

**Output Files:** \
output/analyze_dataset.html - Dataset EDA with the objective of having a overall understading of the data

**Source Directories:** \
*data/cost_data.csv - includes all dataset for training and testing phases of the model in csv format* (needs to be added by who's cloning the repo)
data/cloud-computing.jpeg - image to use in README file


## Setup Virtual Environment
Execute one step at a time.

```
# check existing conda environments
conda env list

# initialize conda (answer no)
conda init bash

# activate bash shell
bash

# build new baseline virtual environment (answer yes)
conda create -n time_series python=3.9

# activate environment
conda activate time_series

# install pipenv (y)
conda install pipenv

# ensure correct folder
cd ~

# create virtual environment folder (and confirm its existence)
mkdir .venv
ls -al

# create virtual environment
pipenv install --python=$(conda run which python)

# test python version
pipenv run python --version
pipenv install time_series scooby

# create kernel
pipenv run ipython kernel install --user --name = task

# needed packages
pipenv install numpy cython matplotlib scipy pandas seaborn scikit-learn plotly sweetviz pathlib
pipenv install pystan==2.19.1.1 prophet

# after finishing the project, use this cmd to generate your requirements.txt file (if necessary)
pip freeze > requirements.txt

# delete kernel & virtual environment
exit
jupyter kernelspec uninstall task
pipenv --rm

```


## Running Steps
The order of execution of the program files is as follows:

- rs-cloud-analytics-modeling.ipynb

This file must be executed, to define all the functions and variables required for modeling operations which leads to the production of the forecast output and also to evaluate the model performance.
