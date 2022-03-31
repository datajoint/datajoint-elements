# Session

## Description of modality, user population 

Session information is part of most data modalities. 
This is a minimal schema with a few number of tables describing the experiment session (date and time, experimenter, subject reference, experiment rig, aims, and notes), 
the project in which the sessions may belong to (project description, DOI, keywords, etc.), data directory for each session. 

## Precursor projects and interviews

All DataJoint pipelines have some form of a session schema or tables. 
The session table is typically in the upstream part of the pipeline, referencing the subject and serves as a common node for other modalities to connect to and expand downstream (e.g. ephys, imaging, video tracking, behavioral events, optogenetic perturbation, etc.). 

## Development

We developed the Session Element under https://github.com/datajoint/element-session. This schema is validated as part of complete workflows in the specific modalities.
