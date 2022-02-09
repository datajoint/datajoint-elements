# DataJoint Elements

![Logo](images/elements-logo.png)

DataJoint Elements provides an efficient approach for neuroscience labs 
to create and manage *scientific data workflows*: the complex multi-step methods
 for data collection, preparation, processing, analysis, and modeling that 
researchers must perform in the course of an experimental study.  The work is 
derived from the developments in leading neuroscience projects and uses the 
[DataJoint framework](https://datajoint.org) for defining, deploying, and 
sharing their data workflows. 

An overview of the principles of DataJoint workflows and the goals of DataJoint 
Elements are described in the position paper 
["DataJoint Elements: Data Workflows for Neurophysiology"](
  https://www.biorxiv.org/content/10.1101/2021.03.30.437358v2).

# Project Structure
* [Management and Policies](management/plan.md)
* [Design Principles](design-principles.md)
* [Guidelines for Adoption](adopt.md)
* [Glossary](glossary.md) 

# Components 
The Resource provides the following main components:

***DataJoint***

> the open-source framework for data pipelines and automated computational 
workflows + related documentation, tools, and utilities.

***DataJoint Elements***

> a collection of curated modules for assembling workflows for the major 
modalities of neurophysiology experiments + related documentation, tools, and 
utilities.

## DataJoint Elements
* [Lab management](https://github.com/datajoint/element-lab)
* [Animal management](https://github.com/datajoint/element-animal)
  * [Example workflow](https://github.com/datajoint/workflow-animal)
* [Experiment session](https://github.com/datajoint/element-session)
* [Extracellular array electrophysiology](https://github.com/datajoint/element-array-ephys)
  * [Example workflow](https://github.com/datajoint/workflow-array-ephys)
* [Calcium imaging](https://github.com/datajoint/element-calcium-imaging)
  * [Example workflow](https://github.com/datajoint/workflow-calcium-imaging)
* [Miniscope imaging](https://github.com/datajoint/element-miniscope)
  * [Example workflow](https://github.com/datajoint/workflow-miniscope)

## DataJoint framework 
* [DataJoint for Python](https://github.com/datajoint/datajoint-python)
* [DataJoint for MATLAB](https://github.com/datajoint/datajoint-matlab)
* [DataJoint Documentation](https://docs.datajoint.org)
* [DataJoint Tutorials](https://tutorials.datajoint.io)
* [Docker image for MySQL server configured for use with DataJoint](https://github.com/datajoint/mysql-docker)

## DataJoint Interfaces 
* [Pharus](https://github.com/datajoint/pharus) — a REST API for interacting 
with DataJoint databases
* [DataJoint LabBook](https://github.com/datajoint/datajoint-labbook) — a 
front-end web interface for viewing and entering data

## DataJoint Online Training  
* [DataJoint CodeBook](https://codebook.datajoint.io) - interactive online tutorials
