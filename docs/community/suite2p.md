# Suite2p

## Sustainability Roadmap between DataJoint Elements and Suite2p

<p align="center">
  <img src="https://github.com/datajoint/datajoint-elements/blob/main/docs/img/suite2p.png?raw=true" width="66" height="87">&nbsp;&nbsp;
  <img src="https://raw.githubusercontent.com/datajoint/datajoint.org/0a05cf5c2530a3595a13fc11f6abac64746d845d/static/images/elements-logo.png" width="300" height="83">
</p>
<br />

## Aim
**DataJoint Elements** and **Suite2p** are two neuroinformatics initiatives in active
  development. The projects develop independently yet they have complementary aims and
  overlapping user communities. This document establishes key processes for
  coordinating development and communications in order to promote integration and
  interoperability across the two ecosystems.

## Projects and Teams

### DataJoint

**DataJoint Elements** — https://elements.datajoint.org — is a collection of open-source
  reference database schemas and analysis workflows for neurophysiology experiments, 
  supported by **DataJoint** — https://datajoint.org — an open-source software 
  framework. The project is funded by the NIH grant U24 NS116470 and led by Dr. Dimitri 
  Yatsenko.
  
The principal developer of DataJoint Elements and the DataJoint framework is the company
DataJoint — https://datajoint.com.

### Suite2p

**Suite2p** — https://www.suite2p.org — is a pipeline for processing calcium imaging
  data. The project is funded by HHMI Janelia Research Campus and led by Dr. Carsen
  Stringer and Dr. Marius Pachitariu.

The principal developers of Suite2p are at the Janelia Research Campus.

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
of DataJoint Elements and Suite2p.

For 2022, the DataJoint Elements POC is Dr. Tolga Dincer (tolga@datajoint.com)

For 2022, the Suite2p POC is Dr. Carsen Stringer (stringerc@janelia.hhmi.org)

### Annual Review

To achieve the aims of coordinated development, the principal developers conduct a joint
annual review of this roadmap document to ensure that the two programs are
well integrated and not redundant. The contents and resolutions of the review will be
made publicly available.

### Licensing

The two parties ensure that relevant software components are developed under licenses
that avoid any hindrance to integration and interoperability between DataJoint Elements
and Suite2p.

## Development Roadmap

- Mechanism to import Suite2p results - Completed 2021 - 
[Element Interface Suite2p module](https://github.com/datajoint/element-interface/blob/main/element_interface/suite2p_loader.py)

- Mechanism to run Suite2p within DataJoint Element - Completed 2022 - 
[Element Calcium Imaging](https://github.com/datajoint/element-calcium-imaging/blob/00df4434fcfd6c1497d7950601248f046170139e/element_calcium_imaging/imaging.py#L267-L299)

- Tutorials on running DataJoint Element with Suite2p - Completed 2021 -
[Workflow Calcium Imaging Jupyter notebooks](https://github.com/datajoint/workflow-calcium-imaging/tree/main/notebooks)

- Integration tests to verify loading Suite2p data - Completed 2021 - 
[Pytests](https://github.com/datajoint/workflow-calcium-imaging/blob/main/tests/test_populate.py)

- Integration tests to verify running Suite2p - Completed 2022 - 
[Pytests](https://github.com/datajoint/workflow-calcium-imaging/blob/main/tests/test_populate.py)

## Citation

If you use Suite2p please cite 
[Pachitariu et al., bioRxiv 2017](https://www.biorxiv.org/content/10.1101/061507v2) in your publications.
