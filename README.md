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

| DataJoint Element | Example workflow | Description |
|:-|:-|:-|
| [Lab management](https://github.com/datajoint/element-lab) | See workflow for session management | [Background](background/lab.md) |
| [Animal management](https://github.com/datajoint/element-animal) | See workflow for session management | [Background](background/animal.md) |
| [Experiment session management](https://github.com/datajoint/element-session) | [Workflow for lab, subject and session management](https://github.com/datajoint/workflow-session) | [Background](background/session.md) |
|  [Extracellular array electrophysiology](https://github.com/datajoint/element-array-ephys) | [Workflow for Neuropixels](https://github.com/datajoint/workflow-array-ephys) | [Background](background/array_electrophysiology.md) |
|  [Calcium imaging](https://github.com/datajoint/element-calcium-imaging) | [Workflow for multiphoton laser scanning](https://github.com/datajoint/workflow-calcium-imaging) | [Background](background/calcium_imaging.md) |
|  [Miniscope imaging](https://github.com/datajoint/element-miniscope) | [Workflow for UCLA Miniscope](https://github.com/datajoint/workflow-miniscope) | [Background](background/miniscope.md) |


### DataJoint Elements -- in development
| DataJoint Element | Example workflow | Description |
|:-|:-|:-|
| [DeepLabCut](https://github.com/datajoint/element-deeplabcut) | [Workflow for pose tracking](https://github.com/datajoint/workflow-deeplabcut) | [Background](background/deeplabcut.md) |
| [Event- and trial-based experiments](https://github.com/datajoint/element-event) | [Workflow for Neuropixels](https://github.com/datajoint/workflow-array-ephys) <br/> [Workflow for multiphoton laser scanning](https://github.com/datajoint/workflow-calcium-imaging) | [Background](background/event.md) |
| [Electrode localization for Neuropixels](https://github.com/datajoint/element-electrode-localization) | [Workflow for Neuropixels](https://github.com/datajoint/workflow-array-ephys) | [Background](background/electrode_localization.md) |
| [Facemap](https://github.com/datajoint/element-facemap)  |  In development |  [Background](background/facemap.md) |


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
- [DataJoint SciViz](https://github.com/datajoint/sci-viz) — a low-code 
  framework for building websites for interactive data visualizaion.

## DataJoint Online Training

- [DataJoint CodeBook](https://codebook.datajoint.io) - interactive online tutorials

## Feedback

DataJoint and DataJoint Elements are supported by NIH grant U24 NS116470 for disseminating open-source software for neuroscience research.  Your feedback is essential for continued funding.  Your feedback also helps shape the technology development roadmap for the DataJoint ecosystem.  Please tell us about your projects by filling out the [DataJoint Census](https://community.datajoint.io).

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
