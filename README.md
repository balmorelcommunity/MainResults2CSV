# MainResults2CSV

This application converts one ore more MainResults.gdx files produced by Balmorel to comma seperated values (csv) files.

## Intro

The mainresults_converter script converts gdx files from GAMS to csv format. 
It is based on the variables defined in the MainResults.gdx produced by the OUTPUT_SUMMARY.inc of Balmorel.
It merges the data for each variable in all gdx files into one csv file and saves it with the a project name and time stamp into the output folder.


## Prerequisites

The following software is needed to run the script:

### programming languages
- python 3.6

### side packages
- gdxpds
- pandas
- openpyxl


## Installation

### With Anaconda
- Install anaconda/miniconda with python 3.7 (https://docs.conda.io/en/latest/miniconda.html)
- Open the anaconda promt
- Navigate to the mainresults_2_gdx folder using the "cd" command and the "tab" key.
- Create a new environment from the environment.yml file [conda instructions](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file)
	> Run: conda env create -f environment.yml

### pip
- to be filled, not tested...


## Execution

1. Set the path to the local gams installation and the project name in the config.py file.
	> Example: C:/GAMS/win64/28.1
	>
	> The project name is only used to name the output csv files.
2. Place all gdx files you want to merge in the input directory in the project folder
	> MainResults2CSV/input
3. The scenario name for each gdx file has to by set directly in the gdx file name by the text in between "MainResults_" and ".gdx"
	> Example: MainResults_"SCENARIONAME_1".gdx
4. Set in the "variable_specification.csv" in the project folder the variables, which shall be included and put TRUE for the indices over which these variables are defined in the OUTPUT_SUMMARY.inc.
	> File format: csv
	>
	> Encoding: utf8
	>
	> Only include variables, that exist in all gdx files! Else, it will cause an error.
	>
	> Save the changes.
5. Activate the environment in the anaconda prompt:
	> Run: activate gdx
6. Navigate to project folder with the "cd" command (use the tab key to suggest folders after each /)
	> Example: cd Desktop/projects/MainResults2CSV
7. Excecute the script:
	> run: python gdx2csv.py
8. All csv files for each variable are now in the output folder.


## Built With

* [gdxpandas](https://pypi.org/project/gdxpds/) - by Elaine T. Hale


## Authors

* **[tilseb](mailto:tilseb@dtu.dk)** - *Initial work*


## License

This project is licensed under the GNU General Public License vers. 3 or later - see the [LICENSE.md](LICENSE.md) file for details


## Acknowledgments

* Hat tip to anyone whose code was used: i.e. Philipp Andreas Gunkel (DTU) ;)

