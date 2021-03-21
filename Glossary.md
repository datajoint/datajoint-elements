# Terminology 

The following are some terms used in the Resource.
<dl>
<dt>DataJoint
<dd>a software framework for database programming directly from matlab and python. Thanks to its support of automated computational dependencies, DataJoint serves as a workflow management system.

<dt>DataJoint Workflow, Experiment Workflow, or simply Workflow
<dd>a formal representation of the steps for executing an experiment from data collection to analysis. Also the software configured for performing these steps. A typical workflow is composed of tables with inter-dependencies and processes to compute and insert data into the tables.

<dt>DataJoint Pipeline
<dd>the data schemas and transformations underlying a DataJoint workflow. DataJoint allows defining code that specifies both the workflow and the data pipeline, and we have used the words "pipeline" and "workflow" almost interchangeably.

<dt>DataJoint Schema
<dd>a software module implementing a portion of an experiment workflow. Includes database table definitions, dependencies, and associated computations.

<dt>DataJoint Elements
<dd>software modules implementing portions of experiment workflows designed for ease of integration into diverse custom workflows.

<dt>djHub
<dd>our team's internal platform for delivering cloud-based infrastructure to support online training resources, validation studies, and collaborative projects.
</dl>
