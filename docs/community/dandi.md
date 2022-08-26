# DANDI

## Sustainability Roadmap  between DataJoint Elements and DANDI Archive
<br>
<p align="center">
  <img src="https://github.com/datajoint/datajoint-elements/blob/main/docs/img/dandi.png?raw=true" width="83" height="83">&nbsp;&nbsp;
  <!-- <img src="https://www.dandiarchive.org/handbook/img/dandi-logo-square_sw.png" width="83" height="83">&nbsp;&nbsp;   -->
  <img src="https://raw.githubusercontent.com/datajoint/datajoint.org/0a05cf5c2530a3595a13fc11f6abac64746d845d/static/images/elements-logo.png" width="300" height="83">
</p>  <br>

## Aim
**DataJoint Elements** and **The DANDI Archive (DANDI)** are two neuroinformatics initiatives in active development. The projects develop independently yet they have complementary aims and overlapping user communities. This document establishes key processes for coordinating development and communications in order to promote integration and interoperability across the two ecosystems.

## Projects and Teams

### DataJoint

**DataJoint Elements** — https://elements.datajoint.org — is a collection of open-source
  reference database schemas and analysis workflows for neurophysiology experiments, 
  supported by **DataJoint** — https://datajoint.org — an open-source software 
  framework. The project is funded by the NIH grant U24 NS116470 and led by Dr. Dimitri 
  Yatsenko.
  
The principal developer of DataJoint Elements and the DataJoint framework is the company
DataJoint — https://datajoint.com.

### Neurodata without Borders (NWB)

**DANDI** - https://dandiarchive.org — is an archive for neurophysiology data, 
providing neuroscientists with a common platform to share, archive, and process data. 
The project is funded by the NIH grant R24 MH117295 and led by Dr. Satrajit S. Ghosh 
and Dr. Yaroslav O. Halchenko.

The principal developers of DANDI are at the Massachusetts Institute of Technology, 
Dartmouth College, Catalyst Neuro, and Kitware.

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
of DataJoint Elements and DANDI.

For 2022, the DataJoint Elements POC is Dr. [Chris Brozdowski](mailto:cbroz@datajoint.com)

For 2022, the DANDI POC is Dr. [Satrajit Ghosh](mailto:satra@mit.edu)

### Annual Review

To achieve the aims of coordinated development, the principal developers conduct a 
joint annual review of this roadmap document to ensure that the two programs are well 
integrated and not redundant. The contents and resolutions of the review will be made 
publicly available.

### Licensing

The two parties ensure that relevant software components are developed under licenses
that avoid any hindrance to integration and interoperability between DataJoint Elements
and DANDI.

## Development Roadmap

- Mechanism to upload to DANDI - Completed 2022 - 
  [Element Interface DANDI module](https://github.com/datajoint/element-interface/blob/main/element_interface/dandi.py)
- Documentation to upload to DANDI - Completed 2022 - 
  [Jupyter notebook](https://github.com/datajoint/workflow-array-ephys/blob/main/notebooks/09-NWB-export.ipynb)