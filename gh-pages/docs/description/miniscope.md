# Miniscope

## Description of modality, user population

Miniature fluorescence microscopes (miniscopes) are a head-mounted calcium imaging full-frame video modality first introduced in 2005 by Mark Schnitzer's lab ([Flusberg et al., Optics Letters 2005](https://pubmed.ncbi.nlm.nih.gov/16190441/)). Due to their light weight, these miniscopes allow measuring the dynamic activity of populations of cortical neurons in freely behaving animals. In 2011, Inscopix Inc. was founded to support one-photon miniscopes as a commercial neuroscience research platform, providing proprietary hardware, acquisition software, and analysis software. Today, they estimate their active user base is 491 labs with a total of 1179 installs. An open-source alternative was launched by a UCLA team led by Daniel Aharoni and Peyman Golshani ([Cai et al., Nature 2016](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5063500/); [Aharoni and Hoogland, Frontiers in Cellular Neuroscience 2019](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6461004/)). In our conversation with Dr. Aharoni, he estimated about 700 labs currently using the UCLA system alone.  The Inscopix user base is smaller but more established. Several two-photon miniscopes have been developed but lack widespread adoption likely due to the expensive hardware required for the two-photon excitation ([Helmchen et al., Neuron 2001](https://pubmed.ncbi.nlm.nih.gov/11580892/); [Zong et al., Nature Methods 2017](https://pubmed.ncbi.nlm.nih.gov/28553965/); [Aharoni and Hoogland, Frontiers in Cellular Neuroscience 2019](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6461004/)).  Due to the low costs and ability to record during natural behaviors, one-photon miniscope imaging appears to be the fastest growing calcium imaging modality in the field today.  In Year 1, we focused our efforts on supporting the UCLA platform due its fast growth and deficiency of standardization in acquisition and processing pipelines. In future phases, we will reach out to Inscopix to support their platform as well.

## Acquisition tools
Daniel Aharoni's lab has developed iterations of the UCLA Miniscope platform.  Based on interviews, we have found labs using the two most recent versions including [Miniscope DAQ V3](http://miniscope.org/index.php/Information_on_the_(previous_Version_3)_Miniscope_platform) and [Miniscope DAQ V4](https://github.com/Aharoni-Lab/Miniscope-v4/wiki).  Labs also use the Bonsai OpenEphys tool for data acquisition with the UCLA miniscope.  Inscopix provides the Inscopix Data Acquisition Software (IDAS) for the nVista and nVoke systems.

## Preprocessing tools
The preprocessing workflow for miniscope imaging includes denoising, motion correction, cell segmentation, and calcium event extraction (sometimes described as "deconvolution" or "spike inference").  For the UCLA Miniscopes, the following [analysis packages](https://github.com/Aharoni-Lab/Miniscope-v4/wiki/Analysis-Packages) are commonly used:

(Package, Developer [Affiliation], Programming Language)

+ [Miniscope Denoising](https://github.com/Aharoni-Lab/Miniscope-v4/wiki/Removing-Horizontal-Noise-from-Recordings), Daniel Aharoni (UCLA), Python
+ [NoRMCorre](https://github.com/flatironinstitute/NoRMCorre), Flatiron Institute, MATLAB
+ [CNMF-E](https://github.com/zhoupc/CNMF_E), Pengcheng Zhou (Liam Paninski’s Lab, Columbia University), MATLAB
+ [CaImAn](https://github.com/flatironinstitute/CaImAn), Flatiron Institute, Python
+ [miniscoPy](https://github.com/PeyracheLab/miniscoPy), Guillaume Viejo (Adrien Peyrache’s Lab, McGill University), Python
+ [MIN1PIPE](https://github.com/JinghaoLu/MIN1PIPE), Jinghao Lu (Fan Wang’s Lab, MIT), MATLAB
+ [CIAtah](https://github.com/bahanonu/calciumImagingAnalysis), Biafra Ahanonu, MATLAB
+ [MiniAn](https://github.com/DeniseCaiLab/minian), Phil Dong (Denise Cai's Lab, Mount Sinai), Python
+ [MiniscopeAnalysis](https://github.com/etterguillaume/MiniscopeAnalysis), Guillaume Etter (Sylvain Williams’ Lab, McGill University), MATLAB
+ [PIMPN](https://github.com/etterguillaume/PIMPN), Guillaume Etter (Sylvain Williams’ Lab, McGill University), Python
+ [CellReg](https://github.com/zivlab/CellReg), Liron Sheintuch (Yaniv Ziv’s Lab, Weizmann Institute of Science), MATLAB
+ Inscopix Data Processing Software (IDPS)
+ Inscopix Multimodal Image Registration and Analysis (MIRA)

Based on interviews with UCLA and Inscopix miniscope users and developers, each research lab uses a different preprocessing workflow.  These custom workflows are often closed source and not tracked with version control software.  For the preprocessing tools that are open source, they are often developed by an individual during their training period and lack funding for long term maintenance.  These factors result in a lack of standardization for miniscope preprocessing tools, which is a major obstacle to adoption for new labs.


## Key projects
Until recently, DataJoint had not been used for miniscope pipelines. However, labs we have contacted have been eager to engage and adopt DataJoint-based workflows in their labs.

+ Adrien Peyrache Lab, McGill University
+ Peyman Golshani Lab, UCLA
+ Daniel Aharoni Lab, UCLA
+ Anne Churchland Lab, UCLA
+ Fan Wang Lab, MIT
+ Antoine Adamantidis Lab, University of Bern
+ Manolis Froudaraki Lab, FORTH
+ Allan Basbaum Lab, UCSF

## Pipeline Development

With assistance from Peyman Golshani’s Lab (UCLA) we have added support for the UCLA Miniscope DAQ V3 acquisition tool and MiniscopeAnalysis preprocessing tool in `element-miniscope` and `workflow-miniscope`.  They have provided example data for development, and will begin validating in March 2021.

Based on interviews, we are considering adding support for the tools listed below.  The deciding factors include the number of users, long term support, quality controls, and python programming language (so that the preprocessing tool can be triggered within the element).

+ Acquisition tools
    + Miniscope DAQ V4
    + Inscopix Data Acquisition Software (IDAS)
+ Preprocessing tools
    + Inscopix Data Processing Software (IDPS)
    + Inscopix Multimodal Image Registration and Analysis (MIRA)
    + MiniAn
    + CaImAn
    + CNMF-E
    + CellReg