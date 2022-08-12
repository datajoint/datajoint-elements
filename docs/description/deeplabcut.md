# DeepLabCut

## Pose Estimation in Neurophysiology

Previous pose estimation methods required reflective markers placed on a subject, as well as multiple expensive high-frame-rate infrared cameras to triangulate position within a limited field. Recent advancements in machine learning have facilitated dramatic advancements in capturing pose data with a video camera alone. In particular, DeepLabCut (DLC) facilitates the use of pre-trained machine learning models for 2- and 3-D non-invasive markerless pose estimation. 

While some alternative tools are either species-specific (e.g., [DeepFly3D](https://github.com/NeLy-EPFL/DeepFly3D)) or uniquely 2D (e.g., [DeepPoseKit](https://github.com/jgraving/DeepPoseKit)), DLC highlights a diversity of use-cases via a [Model Zoo](http://www.mackenziemathislab.org/dlc-modelzoo). Even compared to tools with similar functionality (e.g., [SLEAP](https://github.com/murthylab/sleap) and [dannce](https://github.com/spoonsso/dannce)), DLC has more users, as measured by either GitHub forks or more citations (1600 vs. 900). DLC's trajectory toward an industry standard is attributable to [continued funding](http://www.mackenziemathislab.org/deeplabcutblog/2020/11/18/czidlc), [extensive documentation](https://deeplabcut.github.io/DeepLabCut/docs/intro.html) and both creator- and peer-support. Other comperable tools include [mmpose](https://github.com/open-mmlab/mmpose), [idtracker.ai](idtracker.ai), [TREBA](https://github.com/neuroethology/TREBA), [B-KinD](https://github.com/neuroethology/BKinD), [VAME](https://github.com/LINCellularNeuroscience/VAME), and [MARS](https://github.com/neuroethology/MARS).

## Key Partnerships

Mackenzie Mathis (Swiss Federal Institute of Technology Lausanne) is both a lead developer of DLC and a key advisor on DataJoint open source development as a member of the [Scientific Steering Committee](../management/governance.md).

DataJoint is also partnered with a number of groups who use DLC as part of broader workflows. In these collaborations, members of the DataJoint team have interviewed researchers to understand their needs in experiment workflow, pipeline design, and interfaces.

These teams include:

- Moser Group (Norwegian University of Science and Technology) - see [pipeline design](https://moser-pipelines.readthedocs.io/en/latest/imaging/dlc.html)
- Mesoscale Activity Project (Janelia Research Campus/Baylor College of Medicine/New York University)
- Hui-Chen Lu Lab (Indiana University)
- Tobias Rose Lab (University of Bonn)
- James Cotton Lab (Northwestern University)

## Pipeline Development

Development of the Element began with an [open source repository](https://github.com/MMathisLab/DataJoint_Demo_DeepLabCut) shared by the Mathis team. We further identified common needs across our respective partnerships to offer the following features for single-camera 2D models:

- Training data and parameter management
- Launching model training and automatic model evaluation
- Model metadata management
- Launching inference video analysis and capturing pose estimation output

The workflow handles training data as file sets stored within DLC's project directory. Parameters of the configuration file are captured and preserved. Model evaluation permits direct model comparison, and, when combined with upstream Elements, Element DeepLabCut can be used to generate pose estimation information for each session.
