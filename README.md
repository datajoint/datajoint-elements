# DataJoint Elements 
This resource ("Resource") provides an efficient approach for neuroscience labs to create and manage *scientific data workflows*: the complex multi-step methods for data collection, preparation, processing, analysis, and modeling that researchers must perform in the course of an experimental study. 
The work is derived from the developments in leading neuroscience projects and uses the [DataJoint framework](https://datajoint.io) for defining, deploying, and sharing their data workflows. 

An overview of the principles of DataJoint workflows and the goals of DataJoint Elements are described in the position paper "DataJoint Elements: Building Scientific Workflows for Neurophysiology." (prepint to be posted by 03/25/2021)

## Status 
The beta release of the first DataJoint Elements is scheduled for May 1, 2021.


# Project Structure
* [Team](Team.md)
* [Project Governance](Governance.md)
* [Project Selection Process](Selection.md)
* [Design Principles](DesignPrinciples.md)
* [Quality Assurance](QualityAssurance.md)
* [Outreach Plan](Outreach.md)
* [Licenses and User Agreements](Licenses.md)
* [Glossary](Glossary.md) 

# Components 
The Resource provides the following main components:
<dl>
<dt> DataJoint
<dd> the open-source framework for data pipelines and automated computational workflows + related documentation, tools, and utilities.

<dt> DataJoint Elements
<dd>  a collection of curated modules for assembling workflows for the major modalities of neurophysiology experiments + related documentation, tools, and utilities.
</dl>

## Elements
* Lab management https://github.com/datajoint/element-lab 
* Animal management https://github.com/datajoint/element-animal
  * Example workflow  https://github.com/datajoint/worklow-animal
* Experiment session https://github.com/datajoint/element-session
* Extracellular array electrophysiology https://github.com/datajoint/element-array-ephys
  * Example workflow https://github.com/datajoint/wokrlow-array-ephys
* Calcium imaging https://github.com/datajoint/element-calcium-imaging
  * Example workflow https://github.com/datajoint/workflow-calcium-imaging
* Miniscope imaging https://github.com/datajoint/element-miniscope
  * Example workflow https://github.com/datajoint/workflow-miniscope
   
## Example workflows 
* Electrophysiology workflow with lab and animal management: https://github.com/datajoint/workflow-ephys
* Imaging workflow with lab and animal management https://github.com/datajoint/workflow-imaging


## The DataJoint framework 
* **DataJoint for Python** https://github.com/datajoint/datajoint-python    
* **DataJoint for MATLAB** https://github.com/datajoint/datajoint-matlab    
* **DataJoint Documentation** https://docs.datajoint.io 
* **DataJoint Tutorials** https://tutorials.datajoint.io
* Docker image for MySQL server configured for use with DataJoint:  https://github.com/datajoint/mysql-docker

## Interfaces 
* **Pharus** — a REST API for interacting with DataJoint databases  https://github.com/datajoint/pharus
* **DataJoint Labbook** — a front-end web interface for viewing and entering data  https://github.com/datajoint/datajoint-labbook

## Online Training  
* Interactive online tutorials https://playground.datajoint.io

&copy; DataJoint NEURO, 2021
