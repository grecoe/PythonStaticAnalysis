# Python Static Analysis
<sub>Dan Grecoe - A Microsoft Employee</sub>

When developing code, most organizations require some sort of order and static analysis on your code. The static analysis tool in this repository is for Python code. It should be used to clean up and clear static analysis issues with your code prior to submitting it to your repsitory. 

## Tools Run
There are several tools run on the code. Each of the tools can be found online so I won't describe them here.

- black
- pylint
- mypy
- bandit
- flake8

## Usage
The tool is fairly straightforward to use. Simply launch it from the command line and identify a folder in which to validate:

1. Validation using the command line
    - Required parameter -src [PATH], where PATH is the full disk path to the soure directory to check
    - EX: python static_test.py -src [PATH]
2. Validation using a configuration file
    - Provide a file called static_analysis.json 
    - JSON has a single field called source_folder and it's value is the full disk path of the directory to check
    - EX: python static_test.py

<B>NOTE</B> If the file static_analysis.json exists in the folder of the static_test.py file, it supercedes any parameters passed in. In fact, parameters will be completely ignored. 

## Outputs
The tool black produces no output other than to write to the command window. <b>Also note that black has side effects on your code in place.</b>

The remainder of the output is dropped into a folder (which is created) called test_outputs. Each of the other tools will output their results to a file there on each run. 

# Prerequisite
Create the conda environment that installs the needed toos:

```
conda env create -f environment.yml
```

Activate the environment

```
conda activate StaticAnalysis
```

Now you are ready to run the static_test.py file

# NOTES

- The folder configuration holds any tool configurations that are passed along to the specified tool on running. Look into the static_test.py file to see what file is used for which tool. These files should be kept in sync with your organizations requirements. 


