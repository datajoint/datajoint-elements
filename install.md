# Setup instructions for workflows created with the DataJoint Elements

+ The following document describes the steps to setup a development environment 
so that you can use the DataJoint Elements to build and run a workflow on your 
local machine.

+ The DataJoint Elements can be combined together to create a workflow that 
matches your experimental setup.  We have created example workflows (e.g. 
`workflow-array-ephys`, `workflow-calcium-imaging`) for your reference.  In this
 tutorial we will install these example DataJoint workflows.
 
+ These instructions can be adapted for your custom DataJoint workflow.

+ There are several ways to create a development environment.  Here we will 
discuss one method in detail, and will highlight other methods along the way.  
If you have already set up certain components, feel free to skip those steps.

+ You will need administrative privileges on your system for the following setup
instructions.

## System architecture
![Architecture](/images/install_architecture.png)

+ The above diagram describes the general components for a local DataJoint 
development environment. 

## Install an integrated development environment

![Visual Studio Code](/images/install_vscode.png)

+ DataJoint development and use can be done with a plain text editor in the terminal.  
However, an integrated development environment (IDE) can 
improve your experience.  Several IDEs are available.  In this setup 
example, we will use Microsoft's Visual Studio Code.

+ [Install Visual Studio Code](https://code.visualstudio.com/download)

## Install a relational database

+ A key feature of DataJoint is the ability to connect with a database server 
from a scientific programming environment (i.e. Python or MATLAB) so that your 
experimental data can be stored in the database and downloaded from the 
database.

+ For simplicity of this tutorial we will use the DataJoint Playground tutorial 
database located at `tutorial-db.datajoint.io` which has already been 
configured.  See the section below: [Setup connection to database server](
    #setup-connection-to-database-server).

+ Please note that the tutorial database should not be used for your 
experimental analysis as the storage is not persistent.

+ There are several options if you would like to install a local relational 
database server
    + [Docker image for MySQL server configured for use with DataJoint](
        https://github.com/datajoint/mysql-docker)
    + [Install MariaDB server](https://mariadb.com/kb/en/binary-packages/)

## Install a version control system

+ Git is an open-source, distributed version control system for collaborating 
with software development.  GitHub is a platform that hosts projects managed 
with Git.  As the example DataJoint workflows are hosted on GitHub, we will use 
Git to clone (i.e. download) this repository.

+ For your own DataJoint workflow development we recommended that you use Git and 
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
#TODO this section
+ Register an IPython kernel with Jupyter
    ```
    ipython kernel install --name=workflow-array-ephys
    ```

If you are using jupyter notebook, install a few more helper packages

conda install jupyter nb_conda_kernels
conda install ipykernel
conda install graphviz python-graphviz pydotplus

## Clone and install the repository

+ `workflow-array-ephys`
    <details>
    <summary>Click to expand for details</summary>

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

    + From the root of the cloned repository directory
        ```
        pip install -e .
        ```

    + Note: the `-e` flag will install this repository in editable mode, in case
     there's a need to modify the code (e.g. the `pipeline.py` or `paths.py` 
     scripts). If no such modification required, using `pip install .` is 
     sufficient.

    </details>

+ `workflow-calcium-imaging`
    <details>
    <summary>Click to expand for details</summary>

    + In a terminal and change directory to where you want to clone the 
    repository
        ```
        cd ~/Projects
        ```

    + Clone the repository
        ```
        git clone https://github.com/datajoint/workflow-calcium-imaging
        ```

    + Change directory to `workflow-calcium-imaging`
        ```
        cd workflow-calcium-imaging
        ```

    + From the root of the cloned repository directory
        ```
        pip install -e .
        ```

    + Note: the `-e` flag will install this repository in editable mode, in case
     there's a need to modify the code (e.g. the `pipeline.py` or `paths.py` 
     scripts). If no such modification required, using `pip install .` is 
     sufficient.

    </details>

## Setup connection to database server

+ One way to set up a connection to the database server with DataJoint is to 
create a local configuration file (i.e. `dj_local_conf.json`) at the root of the
 repository folder, with the following template:

+ `workflow-array-ephys`
    <details>
    <summary>Click to expand for details</summary>

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
        "database.prefix": "<username_>",
        "ephys_root_data_dir": "<~/data/ephys_root_data_dir>"
        }
    }
    ```

    </details>

+ `workflow-calcium-imaging`
    <details>
    <summary>Click to expand for details</summary>

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
        "database.prefix": "<username_>",
        "imaging_root_data_dir": "<~/data/imaging_root_data_dir>"
        }
    }
    ```

    </details>

+ Specify the database's `hostname`, `username`, and `password`.
    + For this tutorial we will use the `tutorial-db.datajoint.io` database.  
    Therefore the `hostname` will be `tutorial-db.datajoint.io`.
    
    + The `username` and `password` will be the credentials for your 
    [DataJoint account](https://accounts.datajoint.io).

+ Specify a `database.prefix` which will be the prefix for your schema names.  
For the `tutorial-db` database, you will use your DataJoint username.

+ Setup your data directory (e.g. `ephys_root_data_dir`, 
`imaging_root_data_dir`) following the convention described in the following 
section.

## Directory structure and file naming convention

+ The workflow presented here is designed to work with the directory structure 
and file naming convention as described below.

+ `workflow-array-ephys`
    <details>
    <summary>Click to expand for details</summary>

    + The `ephys_root_data_dir` is configurable in the `dj_local_conf.json`, 
    under `custom/ephys_root_data_dir` variable.

    + The `subject` directory names must match the identifiers of your subjects 
    in the [subjects.csv](./user_data/subjects.csv) script.

    + The `session` directories can have any naming convention.

    + Each session can have multiple probes, the `probe` directories must match 
    the following naming convention:

        `*[0-9]` (where `[0-9]` is a one digit number specifying the probe 
        number)

    + Each `probe` directory should contain:

        + One neuropixels meta file, with the following naming convention:

            `*[0-9].ap.meta`

        + Potentially one Kilosort output folder

    ```
    <ephys_root_data_dir>/
    └───<subject1>/                       # Subject name in `subjects.csv`
    │   └───<session0>/                   # Session directory in `sessions.csv`
    │   │   └───imec0/
    │   │   │   │   *imec0.ap.meta
    │   │   │   └───ksdir/
    │   │   │       │   spike_times.npy
    │   │   │       │   templates.npy
    │   │   │       │   ...
    │   │   └───imec1/
    │   │       │   *imec1.ap.meta
    │   │       └───ksdir/
    │   │           │   spike_times.npy
    │   │           │   templates.npy
    │   │           │   ...
    │   └───<session1>/
    │   │   │   ...
    └───<subject2>/
    │   │   ...
    ```

    </details>

+ `workflow-calcium-imaging`
    <details>
    <summary>Click to expand for details</summary>

    + Note: the `element-calcium-imaging` is designed to accommodate multiple 
    scans per session, however, in this particular `workflow-calcium-imaging`, 
    we take the assumption that there is only one scan per session.

    + The `imaging_root_data_dir` directory is configurable in the 
    `dj_local_conf.json`, under the `custom/imaging_root_data_dir` variable

    + The `subject` directory names must match the identifiers of your subjects 
    in the [subjects.csv](./user_data/subjects.csv) script

    + The `session` directories can have any naming convention
        
    + Each `session` directory should contain:

        + All `.tif` or `.sbx` files for the scan, with any naming convention
        
        + One `suite2p` subfolder per `session` folder, containing the `Suite2p`
         analysis outputs

        + One `caiman` subfolder per `session` folder, containing the `CaImAn` 
        analysis output `.hdf5` file, with any naming convention

    ```
    imaging_root_data_dir/
    └───<subject1>/                     # Subject name in `subjects.csv`
    │   └───<session0>/                 # Session directory in `sessions.csv`
    │   │   │   scan_0001.tif
    │   │   │   scan_0002.tif
    │   │   │   scan_0003.tif
    │   │   │   ...
    │   │   └───suite2p/
    │   │       │   ops1.npy
    │   │       └───plane0/
    │   │       │   │   ops.npy
    │   │       │   │   spks.npy
    │   │       │   │   stat.npy
    │   │       │   │   ...
    │   │       └───plane1/
    │   │           │   ops.npy
    │   │           │   spks.npy
    │   │           │   stat.npy
    │   │           │   ...
    │   │   └───caiman/
    │   │       │   analysis_results.hdf5
    │   └───<session1>/                 # Session directory in `sessions.csv`
    │   │   │   scan_0001.tif
    │   │   │   scan_0002.tif
    │   │   │   ...
    └───<subject2>/                     # Subject name in `subjects.csv`
    │   │   ...
    ```

    </details>

## Setup complete

+ At this point the setup of this workflow is complete.

## Download example data

+ We provide example data to use with the example DataJoint workflows.

+ The data is hosted on DataJoint's Archive which is an AWS storage and can be 
download with [djarchive-client](https://github.com/datajoint/djarchive-client).

+ Install `djarchive-client`
    ```
    pip install git+https://github.com/datajoint/djarchive-client.git
    ```

+ In your python interpreter, import the client
    ```python
    import djarchive_client
    client = djarchive_client.client()
    ```

+ Browse the available datasets
    ```python
    list(client.datasets())
    ```

+ Each datasets has different versions associated with the version of the 
workflow package.  Browse the revisions.
    ```python
    list(client.revisions())                
    ```

+ Get the current version of the workflow
    + `workflow-array-ephys`
        ```python
        from workflow_array_ephys import version
        revision = version.__version__.replace('.', '_')
        revision
        ```

    + `workflow-calcium-imaging`
        ```python
        from workflow_calcium_imaging import version
        revision = version.__version__.replace('.', '_')
        revision
        ```

+ Prepare a directory to store the download data, for example in `/tmp`
    ```
    mkdir /tmp/example_data
    ```

+ Download a given dataset
    + `workflow-array-ephys`
        ```python
        client.download('workflow-array-ephys-test-set', target_directory='/tmp/example_data', revision=revision)
        ```

    + `workflow-calcium-imaging`
        ```python
        client.download('workflow-calcium-imaging-test-set', target_directory='/tmp/example_data', revision=revision)
        ```

+ Directory organization
    + After downloading, the directory will be organized as follows
    
    + We will use this data as an example for the tutorial notebooks for each workflow. If you use for own dataset for the workflow, change the path accordingly.

    + `workflow-array-ephys`
        <details>
        <summary>Click to expand for details</summary>

        ```
        /tmp/example_data/
        - subject6
            - session1
                - towersTask_g0_imec0
                - towersTask_g0_t0_nidq.meta
                - towersTask_g0_t0.nidq.bin
        ```
        
        + The example subject6/session1 data was recorded with SpikeGLX and processed with Kilosort2.
        
        + `element-array-ephys` and `workflow-array-ephys` also support data recorded with OpenEphys.

        </details>

    + `workflow-calcium-imaging`
        <details>
        <summary>Click to expand for details</summary>

        ```
        /tmp/example_data/
        - subject3/
            - 210107_run00_orientation_8dir/
                - run00_orientation_8dir_000_000.sbx
                - run00_orientation_8dir_000_000.mat
                - suite2p/
                    - combined
                    - plane0
                    - plane1
                    - plane2
                    - plane3
        - subject7/
            - session1
                - suite2p
                    - plane0
        ```
        
        + The example subject3 data was recorded with Scanbox and processed with 
        Suite2p.
        
        + The example subject7 data was recorded with ScanImage and processed with 
        Suite2p.
        
        + `element-calcium-imaging` and `workflow-calcium-imaging` also support data
        processed with CaImAn.
        
        </details>

## Interacting with the DataJoint workflow and exploring data

#TODO this section
#TODO add links to other notebooks
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

See `notebooks/run_workflow.ipynb` for detailed instructions on running this workflow.

Once you have your data directory (`imaging_root_data_dir`) configured with the above convention, 
populating the workflow with your data amounts to these 3 steps:

1. Insert meta information (e.g. subject, sessions, equipment, Suite2p analysis parameters etc.) - modify:

2. Import session data - run:
    ```
    python workflow_calcium_imaging/ingest.py
    ```
   
3. Import scan data and populate downstream analyses - run:
    ```
    python workflow_calcium_imaging/populate.py
    ```

+ Rerun step 2 and 3 every time new sessions or processed data becomes available.

+ In fact, step 2 and 3 can be executed as scheduled jobs that will automatically process any data newly placed into the `imaging_root_data_dir`.

## DataJoint LabBook

![LabBook GIF](https://github.com/datajoint/datajoint-labbook/blob/master/docs/sphinx/_static/images/walkthroughDemoOptimized.gif)

+ DataJoint LabBook is a graphical user interface to facilitate working with 
DataJoint workflows.

+ Prerequisites
    + [Install Docker](https://docs.docker.com/get-docker/)
    + [Install Docker Compose](https://docs.docker.com/compose/install/)

+ [Install DataJoint LabBook](
    https://datajoint.github.io/datajoint-labbook/user.html#installation)

+ [DataJoint LabBook GitHub repository](
    https://github.com/datajoint/datajoint-labbook)

+ [DataJoint LabBook Documentation](
    https://datajoint.github.io/datajoint-labbook/)

## Development mode installation

+ This method allows you to modify the source code for example DataJoint 
workflows (e.g. `workflow-array-ephys`, `workflow-calcium-imaging`) and their 
dependencies (i.e. DataJoint Elements).

+ `workflow-array-ephys`
    <details>
    <summary>Click to expand for details</summary>

    + Launch a new terminal and change directory to where you want to clone the 
    repositories
        ```
        cd ~/Projects
        ```

    + Clone the repositories
        ```
        git clone https://github.com/datajoint/element-lab
        git clone https://github.com/datajoint/element-animal
        git clone https://github.com/datajoint/element-session
        git clone https://github.com/datajoint/element-array-ephys
        git clone https://github.com/datajoint/workflow-array-ephys
        ```

    + Install each package with the `-e` option
        ```
        pip install -e ./element-lab
        pip install -e ./element-animal
        pip install -e ./element-session
        pip install -e ./element-array-ephys
        pip install -e ./workflow-array-ephys
        ```

    </details>

+ `workflow-calcium-imaging`
    <details>
    <summary>Click to expand for details</summary>

    + Launch a new terminal and change directory to where you want to clone the 
    repositories
        ```
        cd ~/Projects
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
        pip install -e ./element-lab
        pip install -e ./element-animal
        pip install -e ./element-session
        pip install -e ./element-calcium-imaging
        pip install -e ./workflow-calcium-imaging
        ```

    </details>

