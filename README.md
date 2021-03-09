# Datajoint Elements
**DataJoint Elements** is a library of software modules for organizing data and computations for the major types of neurophysiology experiments. 
The project provides an efficient approach to creating and managing *scientific data workflows*: the complex multi-step methods for data collection, preparation, processing, analysis, and modeling that researchers must perform in the course of an experimental study. 
The work is derived from the developments in leading neuroscience projects that use the [DataJoint framework](https://datajoint.io) for defining, deploying, and sharing their data workflows. 

# Project performance and governance 
## Performer Team 
The project is performed by [DataJoint Neuro](https://djneuro.io) with Dimitri Yatsenko serving as Principal Investigator.
Lead scientists on the project are: Shan Shen, Thinh Nguyen, Kabilar Gunalan, and Edgar Walker. 
Engineers on the project are: Raphael Guzman, Christopher Turner, Maho Sasaki, and Daniel Sitonic. 

## Scientific Steering Group
The project oversight is provided  by the Scientific Steering Group comprising 
* [Mackenzie Mathis (EPFL)](http://www.mackenziemathislab.org/team) 
* [John Cunningham (Columbia U)](https://stat.columbia.edu/~cunningham/)
* [Carlos Brody (Princeton U](https://https://pni.princeton.edu/faculty/carlos-brody)
* [Karel Svoboda (Janelia)](https://www.janelia.org/people/karel-svoboda)
* [Nick Steinmetz (U of Washington)](http://www.nicksteinmetz.com/)
* [Loren Frank (UCSF)](https://franklab.ucsf.edu/)

# What is a DataJoint Element?
In DataJoint, a workflow is organized as a relational database, where each table represents an entity type from the experiment: subjects, sessions, recordings, cells, etc. 

## Validation 

## Experiment Types
p

## Repositories and packages
- GitHub: repos:   datajoint-elements, elements-ephys, elements-  
- DataJoint Elements will comprise a collection of GitHub repos under github.com/datajoint
- DataJoint.io/elements will have links and landing pages. 
- Each repo contains one installable Python package.  No multiple packages per repo.
- The Repo name will be close to the package name.
- Packages will have the name `elements_<example>`: e.g. elements_ephys, elements_animal.

### Elements
- Each package can contain multiple elements 
- 1 element = 1 module = 1 database schema (although nothing prevents users from pointing different modules to the same database schema).
- Most elements will be independent of other elements;  links with other elements are implemented through templated schemas.
- Some elements will be tightly coupled: explicitly depend on other elements using direct import
- Example pipelines will suggest schema names in the form: packagename_modulename
- Each element module will contain the `activate` function that performs checks and calls schema.activate and handles exceptions.

## 
elements-lab
	Elements: 
	- lab 

elements-animal
	Elements:
	- subject       # strain, line
	- care            # genotyping, breeding, housing 

elements-action  (requires elements-animal equivalent upstream)
	- action

elements-session (requires elements-animal, elements-lab equivalent upstream)
	- session:    # session and trials

elements-ephys (upstream: elements-session equivalent)
	- probe 
- ephys

elements-imaging (upstream: elements-session equivalent)
- scan     # include filepath
	- processing

Naming: avoid words 'data', 'table', 'file' using something more concrete. Filepath is okay. 


Each element (module) will have a doc string with the activation code such as: 

from elements_animal import subject
from elements_lab import lab

from elements_ephys import probe, ephys

def activate(schema_name="ephys", probe_schema_name="ephys_probe", extra_objects):
       
     schema.activate(eph

ephys.schema.activate('moser_ephys', extra_objects={probe_schema_name="", ...})
"""
"""
           extra_context={
                            'Session':  lab.Session,     # Session table required, must have:>  
                            'Equipment': Instrument,
                           'get_suite2p_dir':  get_suite2p_dir,    # required if using Suite2p
                            'get_caimain_dir': get_caimain_dir,   # required if using CaImAn
})
""" 
"""

Activate check requirement:
- Verify that extra objects are present and are of the correct type
assert 'Session' in extra_object and extra_object['Session']

schema = dj.schema()

def make()
     get_suite2p_object()

def activate(extra_objects)
       assert 'get_caimain' in extra_objects and insect.iscallable(extract_objects['get_caimain'])
       schema.activate(extra_objects=extra_objects)

Structure of an element module 

"""ELEMENT"""

""" Requirements: 
      Session 
      

required_tables = ['Experiment', 'Scan']
required_functions = []

schema = dj.schema(...)

@schema 
class Scan(dj.Manual):

definition = """
-> Session 
""""


"""Pipeline"""
from element import schema
schema.switch('database', add_context={'Session': Experiment})



