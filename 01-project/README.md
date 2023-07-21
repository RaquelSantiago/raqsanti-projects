# Project Architecture 

- **Project name:** TBD
- **Date Created:** 2023-July-21
- **Author:** Raquel Santiago
- **Description:** Repository for my first project

## Contents

1. [ Objectives ](#objectives)
2. [ Repository folder structure ](#repo_structure)
3. [ Data ](#data)
4. [ Setup Instructions](#setup)
5. ...

<a name="objectives"></a>
## Objectives

TBD - Placeholder objective: *start my portfolio*

<a name="repo_structure"></a>
## Repository folder structure

In this repository structure, there are many utils folders. The reason for this is because there are multiple levels of re-usabiliy.
- **Global Utils**: `src/utils` utils for general purposes - e.g. function to save images with a given name or a function to plot the precision and recall curves as a function of the treshold, given probabilites and the true values.
- **Process Specific Utils**: `src/process_xy/utils` utils for a specific process, like data extraction


**REMINDER to no insert personal data**

This repository is a rough version of [Cookiecutter Template](https://drivendata.github.io/cookiecutter-data-science/).

```
├── README.md                    <- The top-level README
├── config                       <- Configuration info
├── docs                         <- User guide, run guide, project info
├── notebooks                    <- Jupyter notebooks general notebooks
│   └── eda.ipynb                <- Example of a general notebook
|
├── src                          <- Source code for use in this project
├   ├── utils                    <- Utils transversal to all the models
│       ├── aux_functions.py     <- Global utils files
|
├──-----General Processes-------------------------------------------------------
|
├   ├── data_process             <- Source code for general process
│       ├── process.py           <- Task code
│       ├── utils                <- Utils process
│       ├── requirements.txt     <- Requirements for the task
|
├   ├── data_extraction          <- Source code for general process
│       ├── extraction.py        <- Task code
│       ├── utils                <- Utils process
│       ├── requirements.txt     <- Requirements for the task
|
├   ├── process_template         <- Source code for general process
│       ├── template.py          <- Task code
│       ├── utils                <- Utils process
│       ├── requirements.txt     <- Requirements for the task
|
├──-----Models-------------------------------------------------------
|
├   ├── 01-model
│       ├── models*              <- Models specific
│       ├── notebooks            <- Notebooks specific
│       ├── etl                  <- ETL process specific
│           ├── etl.py           <-
│           ├── utils.py         <-
│           ├── requirements.txt <-
│       ├── train                <- Model training pipeline specific to the model
│       ├── inference            <- Model inference pipeline specific to the model
|
├   ├── model_template
│       ├── models*              <- Models specific
│       ├── notebooks            <- Notebooks specific
│       ├── etl                  <- ETL process specific
│           ├── etl.py           <-
│           ├── utils.py         <-
│           ├── requirements.txt <-
│       ├── train                <- Model training pipeline specific to the model
│       ├── inference            <- Model inference pipeline specific to the model
|
├── tests                        <- Tests folder
│    ├── unit                    <- Unit tests
│    ├── functional              <- Functional tests
│    ├── integration             <- Integration tests
└── .gitignore                   <- Files/directories to ignore in repo
```

<a name="data"></a>
## Data

TBD - See the **Setup Instructions** header for more details.

**Data Flow**

The related data will flow trough different stages from source data into the final datasets to be reviewed. To do this, I use the following structure:
- __Raw Zone:__ Initial stage with raw data imported from sources.
- __Structure Zone:__ Intermediate stage to store snapshots of datasets - needed only if having too many intermediate tables from different sources.
- __Consume Zone:__ Final datasets to train models.
- __Sample Zone:__ Samples generated for each model and the final one to be reviewed.

![alt text](images/data_flow.PNG "Data Flow")

```

├── PROJECT                             <- The top-level bucket directory
│   └── PROJECT_20230101                <- Run date
│       └── raw                         <- Raw Zone
│           └── source_01               <- Raw data
│               └── table1.parquet      <- Example table
│           └── source_02               <- Raw notes
│               └── table2.csv          <- Example table
│           └── source_99               <- Labels from another source
│               └── labels.xlsx         <- Example table
│       └── consume                     <- Consume zone
│           └── model_xy                <- Consume tables from model xy
│               └── dataset.parquet     <- Final dataset to be labelled
│       └── sample                      <- Sample zone
│           └── model_xy.parquet        <- results sample
│           └── final_sample.parquet    <- Final sample to be reviewed
│   └── PROJECT_LATEST                  <- Run date
│       └── raw                         <- Raw Zone
│           └── source_01               <- Raw data
│               └── table1.parquet      <- Example table
│           └── source_02               <- Raw notes
│               └── table2.csv          <- Example table
│           └── source_99               <- Labels from another source
│               └── labels.xlsx         <- Example table
│       └── consume                     <- Consume zone
│           └── model_xy                <- Consume tables from model xy
│               └── dataset.parquet     <- Final dataset to be labelled
│       └── sample                      <- Sample zone
│           └── model_xy.parquet        <- results sample
│           └── final_sample.parquet    <- Final sample to be reviewed

```

After each data extraction process, 2 copies will be stored in the bucket/folder, one with the date of the extraction and the other overwritting the 'latest' folder. 
This way I can always keep a snapshot of the data on a specific moment in time and also make sure that the pipeline always processes the latest data extracted without any manual intervention.

<a name="setup"></a>

## Setup Instructions

**Connecting to Data Sources**
Guidelines in README file: 01-project/src/data_extraction/source_01
                           ..


## Testing

Testing is essential to make sure the production code runs flawless.

Run all tests with: `python -m pytest tests/unit`.

...Explain the different types of tests...

## Data Validation

TBC

## Development Guidelines

I like to follow the same coding guidelines:

- Class names are camel case. Eg: __myClass__
- Function names are snake case. Eg: __my_function__
- __Explicit is better than implicit!__ Class names, variables, functions, etc.. should have meaning (avoid using x, a, etc)
- Script names?
- ETL names?
- Main function names?
- Task names?
- etc


## Contributing (if there's more than 1 person using this repo or to prevent committing leakages)
To update the project code, clone or pull the latest version of the repo and create a new branch. 
After finishing the changes, commit the code with appropriate description of the changes, open a pull request and assign at least 1 reviewer.

### Useful git controls:
- __Clone the repo:__ git clone repo
- __Get the latest version of the master:__ git pull origin master
- __Create and switch to a new branch:__ git checkout -b 'branch-name'
- __Add changed files to git staging area:__ git add file1.py file2.py
- __Commit the files in the staging area:__ git commit -m 'brief description of the commit'
- __Open pull request:__ Go to the Git repo, click on 'Open pull request' and follow the guide. Don´t forget to assign a reviewer!
