# Event

## User population

Event- & trial-based experiments have an extensive history in behavioral and cognitive psychology. Fundamentally, data collection is carved up in time according to some ontology. Researchers may repeat Trial conditions in some manner to improve statistical power when contrasting an environmental feature of interest versus a neutral baseline. Neuroscientists, in particular, may be interested in the moments before and after a theoretically-instantaneous Event to look at neurophysiological factors that predict or are predicted by a subject's behavior. What may differ between research groups is the ontology used to carve up time. 

## Key Projects

DataJoint has partnered with the following teams to interview key members, and develop individualized pipelines. By comparing across use-cases, the DataJoint team has developed a highly adaptable workflow to meet most needs, and trialize analyses within an existing DataJoint workflow.

- International Brain Lab
- Mesoscale Activity Project (Janelia Research Campus/Baylor College of Medicine/New York University)
- Jerry Chen Lab (Boston University)
- University of Rochester-New York University-Harvard University U19
- Columbia University U19
- Tobias Rose Lab (University of Bonn)

## Pipeline Development

In addition to the key projects listed below, the DataJoint team met with leaders from both [Neurodata Without Borders](https://www.nwb.org/) and the [Kepecs Lab](https://sites.wustl.edu/kepecslab/), as these groups have both tackled the difficulty of developing ontologies that can cover all possible iterations of behavioral data collection. Our resulting structure is exemplified by the figure below. The language below is tailored to the dependent variable in may neuroscience experiments, behavior, but could be ex

```
|----------------------------------------------------------------------------|
|-------------------------------- Session ---------------------------------|__
|------------------------------- Recording ------------------------------|____
|----- Block 1 -----|______|----- Block 2 -----|______|----- Block 3 -----|___
| Trial 1 || Trial 2 |____| Trial 3 || Trial 4 |____| Trial 5 |____| Trial 6 |
|_|e1|_|e2||e3|_|e4|__|e5|__|e6||e7||e8||e9||e10||e11|____|e12||e13|_________|
|----------------------------------------------------------------------------|
```

- A **Session** is period during which data is collected.
- A **Recording** is some source of data tied to a single modality (e.g., behavior). This may or may not fully capture the session depending on recording latencies or equipment malfunctions. 
- **Block** and **Trial** are a non-instantaneous subsets of Session whose traits often repeat across instances. These periods may be combined or contrasted in downstream analyses. 
- **Trials** may occur within or extend to the intervals between **Blocks**.
- An **Event** (represented with `e` above) is an optionally instantaneous occurrence during a **Session**. 
  + Projects may differ in their need to record event duration (e.g., onset versus duration of subject behavior)
  + **Events** may occur during other categories, or may be unpredictable responses during continuously recorded behavior.
  
Features of Element Event include:

- Pairing of upstream sessions with behavioral recordings
- Multiple recorded attributes for phases of interest (see `Attribute` part tables for `Block` and `Trial`)
- Defining Trial and Event Types as lookup tables
- Optionally activating only the `event` schema for event-based recording, without Trial and Block phases.
- An `AlignmentEvent` table to define the window of interest relative to specific event types.

Each level of the hierarchy (Block, Trial, Event) is designed to be optional to suit a given experiments needs. For example use, visit our [Array Electrophysiology Workflow](https://github.com/datajoint/workflow-array-ephys/).

<!-- At time of writing, the relevant notebook is only on the `event` branch. -->
