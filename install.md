# Setup instructions for DataJoint Elements and Workflows

+ The following document describes the steps to setup a development environment 
so that you can use the DataJoint Elements to build and run a workflow on your 
local machine.

+ The DataJoint Elements can be combined together to create a workflow that 
matches your experimental setup.  We have created example workflows (e.g. 
`workflow-array-ephys`, `workflow-calcium-imaging`) for your reference.  In this
 tutorial we will install workflow-array-ephys.  These instructions can be 
adapted for workflow-calcium-imaging, or your custom workflow.

+ There are several ways to create a development environment.  Here we will 
discuss one method in detail, and will highlight other methods along the way.

+ You will need administrative privileges on your system for the following setup
instructions.

## System Architecture
# TODO insert diagram

## Install an integrated development environment

+ DataJoint development and use can be done with simple text editor and terminal 
application.  However, an integrated development environment (IDE) can help 
improve your experience.  There are several IDEs available.  In this setup 
example, we will use Microsoft's Visual Studio Code.

+ [Install Visual Studio Code](https://code.visualstudio.com/download)

![Visual Studio Code](/images/vscode.png)

## Install a relational database
# TODO this section
+ For simplicity of this tutorial we can use the DataJoint Playground tutorial 
database.

-Database high level discussion (or install)

+ If you would like to install a local relational database server, [MariaDB](
    https://mariadb.org) is one option.
    + [Install MariaDB server](https://mariadb.com/kb/en/binary-packages/)

## Install a version control system
+ Git is an open-source, distributed version control system for collaborating 
with software development.  GitHub is a platform that hosts software developed 
with Git.  As the `workflow-array-ephys` is hosted on GitHub, we will use Git to
clone (i.e. download) this repository.

+ For your own DataJoint workflow develpment we recommended that you use Git and 
GitHub to in collaboration.

+ Many systems come preinstalled with Git.  You can test if have already have
Git installed by typing `git` in a terminal window.

+ If Git is not install on your system, [Install Git](
    https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

## Install a virtual environment

+ A virtual environment allows you to install the packages required for a 
specific project within an isolated environment on your computer.

+ It is highly recommended (though not strictly required) to create a virtual 
environment to run the workflow.

+ Conda and virtualenv are virtual environment managers and you can use either 
option.  Below are the commands for Conda.

+ We will install Miniconda which is a minimal installer for conda.
    + Select the [Miniconda installer link](
        https://conda.io/en/latest/miniconda.html) 
    for your operating system and following the instructions.

+ Create a new conda environment
    + Type the following command into a terminal window
    ```
    conda create -n <environment_name> python=<version>
    ```
    + Example command to create conda environment
        ```
        conda create -n workflow-array-ephys python=3.8.11
        ```

+ Activate the conda environment
    ```
    conda activate <environment_name>
    ```

## Install Jupyter Notebook
# TODO this section
+ Register an IPython kernel with Jupyter
    ```
    ipython kernel install --name=workflow-calcium-imaging
    ```

If you are using jupyter notebook, install a few more helper packages

conda install jupyter nb_conda_kernels
conda install ipykernel
conda install graphviz python-graphviz pydotplus

## Clone the `workflow-array-ephys` repository

+ In a terminal and change directory to where you want to clone the repository
    ```
    cd ~/Projects
    ```

+ Clone the repository
    ```
    git clone https://github.com/datajoint/workflow-array-ephys
    ```

+ Change directory to `workflow-array-ephys`
    ```
    cd workflow-array-ephys
    ```

## Install the `workflow-array-ephys` repository

+ From the root of the cloned repository directory
    ```
    pip install -e .
    ```

+ Note: the `-e` flag will install this repository in editable mode, 
in case there's a need to modify the code (e.g. the `pipeline.py` or `paths.py` 
scripts). If no such modification required, using `pip install .` is sufficient.

# TODO rename element-data-loader
# TODO move ephys readers to element-data-loader
# TODO install element-data-loader

## Configure the `dj_local_conf.json`

At the root of the repository folder, 
create a new file `dj_local_conf.json` with the following template:

```json
{
  "database.host": "<hostname>",
  "database.user": "<username>",
  "database.password": "<password>",
  "loglevel": "INFO",
  "safemode": true,
  "display.limit": 7,
  "display.width": 14,
  "display.show_tuple_count": true,
  "custom": {
      "database.prefix": "<neuro_>",
      "imaging_root_data_dir": "<C:/data/imaging_root_data_dir>"
    }
}
```

+ Specify database's `hostname`, `username`, and `password` properly.

-Connect to database (eg. tutorial-db.datajoint.io)

+ Specify a `database.prefix` to create the schemas.

+ Setup your data directory (`imaging_root_data_dir`) following the convention 
described below.

## Setup complete

+ At this point the setup of this workflow is complete.

## Interacting with the DataJoint workflow and exploring data

# TODO add links to other repositories
+ Connect to database and import tables
    ```
    from workflow_array_ephys.pipeline import *
    ```

+ Query ingested data
    ```
    subject.Subject()
    session.Session()
    ephys.ProbeInsertion()
    ephys.EphysRecording()
    ephys.Clustering()
    ephys.Clustering.Unit()
    ```

+ For a more in-depth exploration of ingested data, please refer to the example [explore notebook](https://github.com/datajoint/workflow-array-ephys/blob/main/notebooks/05-explore.ipynb).

## Development mode installation

This method allows you to modify the source code for `workflow-array-ephys`, 
`element-array-ephys`, `element-animal`, `element-session`, and `element-lab`.

+ Launch a new terminal and change directory to where you want to clone the 
repositories
    ```
    cd C:/Projects
    ```
+ Clone the repositories
    ```
    git clone https://github.com/datajoint/element-lab
    git clone https://github.com/datajoint/element-animal
    git clone https://github.com/datajoint/element-session
    git clone https://github.com/datajoint/element-calcium-imaging
    git clone https://github.com/datajoint/workflow-calcium-imaging
    ```
+ Install each package with the `-e` option
    ```
    pip install -e ./workflow-calcium-imaging
    pip install -e ./element-session
    pip install -e ./element-lab
    pip install -e ./element-animal
    pip install -e ./element-calcium-imaging
    ```

## DataJoint LabBook
+ DataJoint LabBook is a graphical user interface to facilitate working with 
DataJoint workflows.

![LabBook GIF](https://github.com/datajoint/datajoint-labbook/docs/sphinx/\
_static/images/walkthroughDemoOptimized.gif)

+ Prerequisites
    + [Install Docker](https://docs.docker.com/get-docker/)
    + [Install Docker Compose](https://docs.docker.com/compose/install/)

+ [Install DataJoint LabBook](
    https://datajoint.github.io/datajoint-labbook/user.html#installation)

+ [DataJoint LabBook GitHub repository](
    https://github.com/datajoint/datajoint-labbook)

+ [DataJoint LabBook Documentation](
    https://datajoint.github.io/datajoint-labbook/)
