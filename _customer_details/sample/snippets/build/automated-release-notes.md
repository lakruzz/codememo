---
---
<!-- markdownlint-disable MD041 -->
**_Note:<br/>The following is a curated mix of illustrative findings from various anonymized reports_**

### Release Notes are manually created

The release notes are handled in Confluence. It is a manual process and it is time consuming. The Jira issues are extracted and post-processed for the final release note. It is glue-on quality - not built-in quality. The release note cannot be generated based on a meta-system like Jira alone. It does not have the source revision time record. Jira issues and releases in Jira do not understand relationship of changes in the SCM system.

#### Design your Jira issues for data extraction

It is important to configure you schema in Jira, so it stores all needed information about the logical change. Add a status which tells if it should be listed in the release note. Not every task should be listed in a release note that the end user sees. Add a field for end-user description which can be extracted if public.

#### Generate different release note for different stakeholders

The different stakeholders will have different needs. At least it makes sense to have two generated release notes. One for R&D which is used for meta data quality checks and used to monitor 'release-readiness'. The second is a public release note which is reporting what external stakeholders need to know. Meaning, which features have been implemented and which publicly known errors have been corrected.

### Create your release note as a record of your SCM system

The only correct place to initialize your release note is from your SCM system as it is 'the' one and only truth about this particular revision compared to previous revision/releases.

### Use a release note generator based on SCM system (M)

Given that the systems and process are designed for automation the report can be generated. Any changes to data for the release note is changed/added/removed at the root source of the information. This means that the release note can be regenerate based on the updated data.

#### Add the generator to the pipeline

Add the release note generation to the pipeline. It then becomes artifact as any other product generated as part of the pipeline. It will be an important artifact for the tester and product owner as it shows exact progress of the software for later promotion decisions on this particular revision.

#### Use the R&D release note as a consistency check (S)

As part of the release gate it is possible to monitor the release readiness where the release DoD is programmed/implemented. This is to harvest traceability and use it as a consistency check.

The consistency checks could look something like the following

- Do all SCM change-sets have a related Jira issue
- Are all the Jira issues in a correct status
- Do we have all the changes related to all the Jira issues for this release
- Do the change sets, based on the Jira issues, have the needed reviews in the correct status

### Security review process and documentation is manual

The security review is needed for the safety reaction of the device. Changes to these algorithms are related to a special and mandatory review that needs to be documented and signed-off as part of the release process. The review is not tool-aided and is currently documented in the Jira issue. It is a manual process to gather the reviews to create the document that is signed by the security-officer.

#### Implement a solid review process and automatically generate the documentation

It is advised to implement Crucible/FishEye(already available) as the front-end for the review. It handles the statuses of the reviews. Given the data and status is available in the Atlassian suite it is possible to auto generate the review report ready for signature.

<!-- cspell:words Praqmatic -->

An option is to use [PAC](https://github.com/Praqma/Praqmatic-Automated-Changelog "Praqmatic Automated Changelog"){: target="_blank"} as a foundation, it's an open source tool that can be extended to also generate the review report.
