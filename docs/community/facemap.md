# Facemap

## Sustainability Roadmap between DataJoint Elements and Facemap

<p align="center">
  <img src="https://github.com/datajoint/datajoint-elements/blob/main/docs/img/facemap.png?raw=true" width="300" height="55" align="left">&nbsp;&nbsp;
  <img src="https://raw.githubusercontent.com/datajoint/datajoint.org/0a05cf5c2530a3595a13fc11f6abac64746d845d/static/images/elements-logo.png" width="120" height="92" align="right">
</p>  

## Aim
**DataJoint Elements** and **Facemap** are two neuroinformatics initiatives in active
development. The projects develop independently yet they have complementary aims and
overlapping user communities. This document establishes key processes for coordinating
development and communications in order to promote integration and interoperability
across the two ecosystems.

## Projects and Teams

### DataJoint

**DataJoint Elements** — https://elements.datajoint.org — is a collection of open-source
  reference database schemas and analysis workflows for neurophysiology experiments, 
  supported by **DataJoint** — https://datajoint.org — an open-source software 
  framework. The project is funded by the NIH grant U24 NS116470 and led by Dr. Dimitri 
  Yatsenko.
  
The principal developer of DataJoint Elements and the DataJoint framework is the company
DataJoint — https://datajoint.com.

### Facemap

**Facemap** - https://github.com/MouseLand/facemap — is a pipeline for processing
imaging data. The project is funded by HHMI Janelia Research Campus and led by
Dr. Carsen Stringer and Atika Syeda.

The principal developers of Facemap are at the Janelia Research Campus.

## General Principles

### No obligation

The developers of the two ecosystems acknowledge that this roadmap document creates no
contractual relationship between them but they agree to work together in the spirit of
partnership to ensure that there is a united, visible, and responsive leadership and to
demonstrate administrative and managerial commitment to coordinate development and
communications.

### Coordinated Development

The two projects will coordinate their development approaches to ensure maximum
interoperability. This includes:

-   coordinated use of terminology and nomenclatures
-   support for testing infrastructure: unit testing and integration testing
-   a coordinated software release process and versioning
-   coordinated resolution of issues arising from joint use of the two tools

### Points of Contact

To achieve the aims of coordinated development, both projects appoint a primary point of
contact (POC) to respond to questions relating to the integration and interoperability 
of DataJoint Elements and Facemap.

For 2022, the DataJoint Elements POC is Dr. Tolga Dincer (tolga@datajoint.com)

For 2022, the Facemap POC is Dr. Carsen Stringer (stringerc@janelia.hhmi.org)

### Annual Review

To achieve the aims of coordinated development, the principal developers conduct a joint
annual review of this roadmap document to ensure that the two programs are
well integrated and not redundant. The contents and resolutions of the review will be
made publicly available.

### Licensing

The two parties ensure that relevant software components are developed under licenses
that avoid any hindrance to integration and interoperability between DataJoint Elements 
and Facemap.

## Development Roadmap

- Mechanism to import Facemap results - Completed 2022 - 
[Element Facemap](https://github.com/datajoint/element-facemap/blob/0ccab4ec6731cd612e7cf61a221c64fb9bf22566/element_facemap/facial_behavior_estimation.py#L389-L405)

- Mechanism to run Facemap within DataJoint Elements - Completed 2022 - 
[Element Facemap](https://github.com/datajoint/element-facemap/blob/0ccab4ec6731cd612e7cf61a221c64fb9bf22566/element_facemap/facial_behavior_estimation.py#L259-L266)

- Tutorials on running DataJoint Element with Facemap - Under development 

- Integration tests to verify loading Facemap data - Under development

- Integration tests to verify running Facemap - Under development

## Citation

If you use Facemap please cite 
[Stringer*, Pachitariu*, et al., Science 2019](https://doi.org/10.1126%2Fscience.aav7893) in 
your publications.
