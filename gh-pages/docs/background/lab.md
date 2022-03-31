## Description of modality, user population
Most pipelines track some information about the lab, including the facilities, experiment rigs, and users. All interviewed labs have some version of these elements. They also have custom interfaces and GUIs for data entry.

## Precursor projects and interviews
Over the past few years, several labs have developed DataJoint-based pipelines for lab management. Our team collaborated with several of them during their projects. Additionally, we interviewed these teams to understand their experiment workflow, associated tools, and interfaces.
These teams include:
+ [International Brain Laboratory](https://github.com/int-brain-lab/IBL-pipeline)
+ BrainCoGs (Princeton Neuroscience Institute), [Python pipeline](https://github.com/BrainCOGS/U19-pipeline_python), [MATLAB pipeline](https://github.com/BrainCOGS/U19-pipeline-matlab)
+ MoC3 (Columbia Zuckerman Institute)
    + [Churchland Lab](https://github.com/ZuckermanBrain/datajoint-churchland/tree/master/churchland_pipeline_python)
    + Costa Lab (private repository)
    + [Hillman Lab](https://github.com/ZuckermanBrain/datajoint-hillman)

## Development and validation
Through our interviews and direct collaboration on the precursor projects, we identified the common motifs in the lab schemas to create the Lab Management Element.
This element works for diverse downstream pipelines and is always used in combination with other elements for specific experiments. As such, it is validated jointly with the acquisition elements such as the [Extracellular Array Electrophysiology Element](https://github.com/datajoint/element-array-ephys) and [Calcium Imaging Element](https://github.com/datajoint/element-calcium-imaging).
