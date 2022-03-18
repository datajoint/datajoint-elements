# DataJoint Elements for Neurophysiology

![Logo](https://raw.githubusercontent.com/datajoint/datajoint.org/0a05cf5c2530a3595a13fc11f6abac64746d845d/static/images/elements-logo.png)

DataJoint Elements provides an efficient approach for neuroscience labs
to create and manage _scientific data workflows_: the complex multi-step methods
for data collection, preparation, processing, analysis, and modeling that
researchers must perform in the course of an experimental study. The work is
derived from the developments in leading neuroscience projects and uses the
[DataJoint framework](https://datajoint.org) for defining, deploying, and
sharing their data workflows.

**_DataJoint_**

> the open-source framework for data pipelines and automated computational
> workflows + related documentation, tools, and utilities.

**_DataJoint Elements_**

> a collection of curated modules for assembling workflows for the major
> modalities of neurophysiology experiments + related documentation, tools, and
> utilities.

An overview of the principles of DataJoint workflows and the goals of DataJoint 
Elements are described in the position paper
["DataJoint Elements: Data Workflows for Neurophysiology"](https://www.biorxiv.org/content/10.1101/2021.03.30.437358v2).

# Project Structure

- [Management and Policies](management/plan.md)
- [Design Principles](usage/design-principles.md)
- [Guidelines for Adoption](usage/adopt.md)
- [Glossary](usage/glossary.md)

## DataJoint Elements

- [Lab management](https://github.com/datajoint/element-lab)
- [Animal management](https://github.com/datajoint/element-animal)
- [Experiment session](https://github.com/datajoint/element-session)
  - [Example workflow for lab, subject and session management](https://github.com/datajoint/workflow-session)
- [Extracellular array electrophysiology for Neuropixels](https://github.com/datajoint/element-array-ephys)
  - [Example workflow](https://github.com/datajoint/workflow-array-ephys)
- [Calcium imaging](https://github.com/datajoint/element-calcium-imaging)
  - [Example workflow](https://github.com/datajoint/workflow-calcium-imaging)
- [Miniscope imaging](https://github.com/datajoint/element-miniscope)
  - [Example workflow](https://github.com/datajoint/workflow-miniscope)

### DataJoint Elements in development
- [DeepLabCut](https://github.com/datajoint/element-deeplabcut)
- [Event- and trial-based experiments](https://github.com/datajoint/element-event)
- [Electrode localization for Neuropixels](https://github.com/datajoint/element-electrode-localization)
- [Facemap](https://github.com/datajoint/element-facemap)

## DataJoint framework

- [DataJoint for Python](https://github.com/datajoint/datajoint-python)
- [DataJoint for MATLAB](https://github.com/datajoint/datajoint-matlab)
- [DataJoint Documentation](https://docs.datajoint.org)
- [DataJoint Tutorials](https://tutorials.datajoint.io)
- [Docker image for MySQL server configured for use with DataJoint](https://github.com/datajoint/mysql-docker)

## DataJoint Interfaces

- [Pharus](https://github.com/datajoint/pharus) — a REST API for interacting
  with DataJoint databases
- [DataJoint LabBook](https://github.com/datajoint/datajoint-labbook) — a
  front-end web interface for viewing and entering data

## DataJoint Online Training

- [DataJoint CodeBook](https://codebook.datajoint.io) - interactive online tutorials

## Citation

If your work uses DataJoint or DataJoint Elements, please cite the following:

**_DataJoint_**
> Yatsenko D, Reimer J, Ecker AS, Walker EY, Sinz F, Berens P, Hoenselaar A, Cotton RJ, 
> Siapas AS, Tolias AS. DataJoint: managing big scientific data using MATLAB or Python. 
> bioRxiv. 2015 Jan 1:031658.


**_DataJoint Elements_**
> Yatsenko D, Nguyen T, Shen S, Gunalan K, Turner CA, Guzman R, Sasaki M, Sitonic D, 
> Reimer J, Walker EY, Tolias AS. DataJoint Elements: Data Workflows for 
> Neurophysiology. bioRxiv. 2021 Jan 1.