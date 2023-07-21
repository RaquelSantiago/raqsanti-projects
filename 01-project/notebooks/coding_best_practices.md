# Coding Best Practices

## General

- *Version Control*

  - All code must be on Github 

  - Clean all notebooks before uploading to github to avoid uploading sensitive information

  - Github repos should follow the same structure (cookiecutter template) 

- *Comments*

  - The code logic should be documented in a high level in README files in the repo and the scripts/notebooks should contain detailed comments explaining each function/logic. The idea is that anyone can read a script and understand exactily what is being done (including ourselves, a few months after not looking at it) 

  - All comments should be in English

  - Add comments to your code to ensure it is readable and maintainable

  - Add config management information to start of code

- *Code Validation*

  - All datasets should be validated (against things like Business Intelligence reports etc) 

  - The most critical parts of your code should be unit tested by the data scientist who wrote it 

  - All code must be peer reviewed (before being put into pilot or production) 

- *Code Construction*

  - All code to be built in functions and made reusable (where possible and where makes sense) 

  - All code should be as automated as possible when put into production for low cost maintenance 

  - Secrets/passwords should be stored in the secrets manager 

  - Use pipelines where possible for modeling to avoid errors/data leakage 

  - Consider replacing jupyter notebooks for python scripts + console to faster iterate between dev/prod 

  - Try to package general code (e.g. connections) to centralize maintenance 

  - Try to keep functions and utils in separated from the main file/notebook to make it cleaner 

- *Syntax and Formatting*

  - Indent your code (as appropriate for the language) for readability

  - Keep capitalization consistent within your script

  - Try to use a meaningful naming convention for variables, tables etc
