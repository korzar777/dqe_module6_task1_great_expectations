# DQE Module Great Expectation
 - data source added for the TRN database testing
 - several table assets created for testing tables Jobs, Employees
 - test suits for each table created. 
 - list of testing metrics added to each test suit
 - testing consolidated to checkpoint and executed from it
 - profiler metrics also generated and saved to testsuit.
 - for profiler testsuit separate asset and checkpoing created to allow separate run
 - results of executed are reported using data docs report
 - for execution jupyter notebooks were created (one for DB testing and one for profile metrics)

## Project structure
- great_expectation folder - root folder
- great_expectation.yml - includes main configuration including datasources and assets
- checkpoints - stores checkpoints; 
- expectations - jobs and employees expectations + profile expectations
- notebooks - allows to run tests

## Preparing environment for tests execution
```bash
python -m venv venv 
venv\Scripts\activate
pip install -r requirements.txt
```

## Running notebook from local server
```bash
cd <project_folder>
jupyter notebook --no-browser --port=8888
```

## Notebook usage 
after notebook server started
 - take the link to server using string "To access the server, open this file in a browser .. Or copy and paste one of these URLs"
 - open provided link in browser
 - find notebook in folder great_expectations\notebooks\  

1. NoteBook trn_test_notebook.ipynb
    - includes base steps (shows project structure assets, suits and so on)
    - load checkpoint checkpoints\trn_checkpoint.yml
    - makes testing of suites jobs.jobs_tests and employees.employees_tests
2. NoteBook profiler_preparations_notebook.ipynb
   - shows steps of working with profiler
   - load checkpoint trn_profile_checkpoint.yml
   - Makes testing of suite jobs_profile

## Testsuits:
    - jobs.jobs_tests - 5 metrics; 1 is failing (manually set to fail)
    - employees.employees_tests - 5 metrics; 1 is failing (manually set to fail)
    - jobs_profile - long list of metrics generated by profile (for all columns except 1). Several metrics are failing.
 
## Latest report 
 latest report is loaded to folder
 great_expectations\report\data_docs\local_site\