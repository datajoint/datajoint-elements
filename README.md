# Datajoint Elements
This is the main page for **DataJoint Elements** — a library of software modules for organizing data and computations in neurophysiology experiments. 
The project provides an efficient approach to creating and managing *scientific data workflows*: the complex multi-step methods for data collection, preparation, processing, analysis, and modeling that researchers must perform in the course of an experimental study. 
The work is derived from the developments in leading neuroscience projects that use the [DataJoint framework](https://datajoint.io) for defining, deploying, and sharing their data workflows. 

## Status 
This resource will launch on May 1, 2021.

The overview of the principles of DataJoint pipelines and the goals of DataJoint Elements are described in the position paper "DataJoint Elements: Building Scientific Workflows for Neurophysiology." (prepint to be posted by 03/25/2021)

# Project performance and governance 

## Performer Team 
The project is performed by [DataJoint Neuro](https://djneuro.io) with Dimitri Yatsenko serving as Principal Investigator.

The lead scientists on the project are:

* Dimitri Yatsenko
* Thinh Nguyen
* Shan Shen
* Kabilar Gunalan
* Edgar Y. Walker

Engineers on the project are:
* Raphael Guzman
* Christopher Turner
* Maho Sasaki
* Daniel Sitonic

## Scientific Steering Group
The project oversight and guidance is provided by the Scientific Steering Group comprising 
* [Mackenzie Mathis (EPFL)](http://www.mackenziemathislab.org/team) 
* [John Cunningham (Columbia U)](https://stat.columbia.edu/~cunningham/)
* [Carlos Brody (Princeton U)](https://https://pni.princeton.edu/faculty/carlos-brody)
* [Karel Svoboda (Janelia)](https://www.janelia.org/people/karel-svoboda)
* [Nick Steinmetz (U of Washington)](http://www.nicksteinmetz.com/)
* [Loren Frank (UCSF)](https://franklab.ucsf.edu/)

## Policies
The project observes the following policies:
* [Project Selection Process](./Selection.md)
* [Quality Assurance](./QualityAssurance.md)
* [Outreach Plan](./OutReach.md)

# Some Terminology 
<dl>

<dt>DataJoint 
<dd>a software framework for database programming directly from matlab and python. Thanks to its support of automated computational dependencies, DataJoint serves as a workflow management system.

<dt>DataJoint Workflow, Experiment Workflow, or simply Workflow 
<dd>a formal representation of the steps for executing an experiment from data collection to analysis. Also the software configured for performing these steps.

<dt>DataJoint Pipeline
<dd>the data schemas and transformations underlying a DataJoint workflow. DataJoint allows defining code that specifies both the workflow and the data pipeline, and we have used the words "pipeline" and "workflow" almost interchangeably.  

<dt>DataJoint Schema 
<dd>a software module implementing a portion of an experiment workflow. Includes database table definitions, dependencies, and associated computations. 

<dt>DataJoint Elements
<dd>software modules implementing portions of experiment workflows designed for ease of integration into diverse custom workflows.

<dt>djHub 
<dd>our team's internal platform for delivering cloud-based infrastructure to support training infrastructure and validation studies.

</dl>

# Components 

## The DataJoint framework 
* **DataJoint for Python** https://github.com/datajoint/datajoint-python    
* **DataJoint for MATLAB** https://github.com/datajoint/datajoint-matlab    
* **DataJoint Documentation** https://docs.datajoint.io 
* **DataJoint Tutorials** https://tutorials.datajoint.io
* Docker image for MySQL server configured for use with DataJoint:  https://github.com/datajoint/mysql-docker

## Interfaces 
* **Pharus** -- a REST API for interacting with DataJoint databases  https://github.com/datajoint/pharus
* **DataJoint Labbook** -- a front-end web interface for viewing and entering data  https://github.com/datajoint/datajoint-labbook

## Elements 
* Lab management https://github.com/datajoint/elements-lab 
* Animal management https://github.com/datajoint/elements-animal
* Extracellular electrophysiology https://github.com/datajoint/elements-ephys
* Calcium imaging https://github.com/datajoint/elements-imaging

## Example workflows 
* Electrophysiology workflow with lab and animal management: https://github.com/datajoint/workflow-ephys
* Imaging workflow with lab and animal management https://github.com/datajoint/workflow-imaging

## Online Training Infrastructure 
* Interactive online tutorial https://playground.datajoint.io
