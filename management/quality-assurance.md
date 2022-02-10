# Quality Assurance

DataJoint and DataJoint Elements serve as a framework and starting points for numerous new projects, setting the standard of quality for data architecture and software design. To ensure higher quality, the following policies have been adopted into the software development lifecycle (SDLC).

## Coding Standards

When writting code, the following principles should be observed.

- **Style**: Code shall be written for clear readability. Uniform and clear naming conventions, module structure, and formatting requirements shall be established across all components of the project. Python's [PEP8](https://www.python.org/dev/peps/pep-0008/#naming-conventions) standard offers clear guidance to this regard which can similarly be applied to all languages.
- **Maintenance Overhead**: Code base size should be noted to prevent large, unnecessarily complex solutions from being introduced. The idea is that the larger the code base, the more there is to review and maintain. Therefore, we should aim to find a compromise where we can keep the code base from becoming too large without adding convoluted complexity.
- **Performance**: Performance drawbacks should be avoided, controlled, or, at least, be properly monitored and justified. For instance: memory management, garbage collection, disk reads/writes, and processing overhead should be regarded to ensure that an efficient solution is achieved.

## Automated Testing

All components and their revisions must include appropriate automated software testing to be considered for release. The core framework must undergo thorough performance evaluation and comprehensive integration testing.

Generally, this includes tests related to:

- **Syntax**: Verify that the code base does not contain any syntax errors and will run or compile successfully.
- **Unit & Integration**: Verify that low-level, method-specific tests (unit tests) and any tests related coordinated interface between methods (integration tests) pass successfully. Typically, when bugs are patched or features are introduced, unit and integration tests are added to ensure that the use-case intended to be satisfied is accounted for. This helps us prevent any regression in functionality.
- **Style**: Verify that the code base adheres to style guides for optimal readability.
- **Code Coverage**: Verify that the code base has similar or better code coverage than the last run.

## Code Reviews

When introducing new code to the code base, the following will be required for acceptance by DataJoint core team into the main code repository.

- **Independence**: Proposed changes should not directly alter the code base in the review process. New changes should be applied separately on a copy of the code base and proposed for review by the DataJoint core team. For example, apply changes on a GitHub fork and open a pull request targeting the `main` branch once ready for review.
- **Etiquette**: An author who has requested for a code for review should not accept and merge their own code to the code base. A reviewer should not commit any suggestions directly to the authors proposed changes but rather should allow the author to review. 
- **Coding Standards**: Ensure the above coding standards are respected.
- **Summary**: A description should be included that summarizes and highlights the notable changes that are being proposed.
- **Issue Reference**: Any bugs or feature requests that have been filed in the issue tracker that would be resolved by acceptance should be properly linked and referenced.
- **Satisfy Automated Tests**: All automated tests associated with the project will be verified to be successful prior to acceptance.
- **Documentation**: Documentation should be included to reflect any new feature or behavior introduced.
- **Release Notes**: Include necessary updates to the release notes or change log to capture a summary of the patched bugs and new feature introduction. Proper linking should be maintained to associated tickets in issue tracker and reviews.

## Alpha Release Process

For the workflows and their revisions, the initial development and internal testing, the code will be released in *Alpha*. During this phase, we will engage external research teams to test and validate the complete workflows in real-life experiments with our team's engineering support. During this phase, significant design changes may be performed and not all features may be completely developed. However, several features should be usable and suitable for testing and validation.

### Criteria to participate as validation sites
+ The participating lab/group has an existing DataJoint pipeline for the Element(s) to be connected to
+ The DataJoint pipeline code base is hosted as a Github repository (either public or private)
+ The participating lab/group has existing datasets in the format supported by the Element(s) for the purpose of this validation
+ The participating lab/group has a dedicated point of contact person to work closely with DataJoint&reg; engineering team for this validation effort

### Criteria for a successful validation
+ Able to connect the Element(s) to existing pipeline and all schemas/tables declared without errors
+ Successful ingestion of data for at least 2 experimental sessions
+ Inspection/verification that the data are ingested correctly by the participating lab/group - e.g. manual inspection of ingested traces, plotting of spatial footprints, spike trains, etc. to confirm correctness of ingested data 


## Beta Release Process

After the initial validation phase, we make the workflows available to the general public with a warning of *Beta* status and that the released code may be subject to errors and changes. During this phase, feature development should be complete with a focus on collecting user feedback to make design improvements and bug fixes.

## Official Release Process

After gaining confidence of user satisfaction by resolving concerns raised in *Beta*, the workflows are declared officially released and announced to the community.

## Maintenance Support Lifecycle

Revision of the workflows will be released with a version specification that clearly identifies whether in *Alpha*, *Beta*, or *Official* release status. Quality assurance process will be followed for all iterations and new designs. If the updates require changes in the design of the database schema or formats, a process for data migration will be provided. 

## User Feedback & Issue Tracking

All components will be organized in GitHub repositories with guidelines for contribution, feedback, and issue submission to the issue tracker. For more information on the general policy around issue filing, tracking, and escalation, see the [DataJoint Open-Source Contribute](https://docs.datajoint.io/python/community/02-Contribute.html) policy. Typically issues will be prioritized based on their criticality and impact. If new feature requirements become apparent, this may trigger the creation of a separate workflow or a major revision of an existing workflow.
