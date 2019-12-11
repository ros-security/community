# ROS 2 Security Working Group
The Security Working Group's mission is to advocate for and implement security features within ROS 2.  The working group negotiates a balance between the benefits of security and the enablement of technology, striving for a secure-by-default design which can be customized to suit a targeted security profile.

This document outlines the governance of the ROS 2 Security Working Group.  Updates to this document will be handled in the same manner as other project updates governed by the Working Group.

## Subprojects
A significant portion of the Security Working Group's mission is achieved by maintaining ROS projects.  The following projects are owned by this Working Group:
* _TBD:  list of project names_

### Adding subprojects
To request that the Security Working Group take on ownership and maintainership of a particular project, create a new issue in this repository using the appropriate issue template. You may be requested to present your proposal at the next Security Working Group meeting. Approvers will vote on whether or not the Working Group will accept the project.

### Standards for subprojects
Subprojects must meet the following criteria:
* Builds must pass against ROS 2 master
* Test suite must pass
* Test coverage must be greater than 50%
* The ROS 2 standard linter set must be enabled and adhered to
* Builds must have 0 warnings

## Governance
These guidelines are designed exclusively to help the Working Group achieve its mission, but are subject to change should they become cumbersome or ineffective.

### Meetings
* The working group typically meets on the last Tuesday of each month, at alternating times to accomodate our community's varied timezones
* Meetings are announced and an agenda created on the ROS Discourse using the [wg-security tag](https://discourse.ros.org/tags/wg-security)
* Meeting notes are kept on the [ROS Wiki](http://wiki.ros.org/ROS2/WorkingGroups/Security)
* Meetings are recorded and available [on YouTube](https://www.youtube.com/playlist?list=PLpUh4ScdBhSMaEekJ8xeAAGmWUgR9S1K_)

### Roles
Security Working Group members may act in one or more of the following roles:
* __Member__
  * Attend a majority of the Security Working Group meetings
  * Responsible for triaging issues
* __Reviewer__
  * All reviewers are members
  * Responsible for reviewing pull requests
* __Approver__
  * All approvers are reviewers
  * Responsible for approving and merging pull requests
  * Responsible for vetting and accepting new projects into the Working Group

To become a member or change role, create an issue in this repository using the appropriate issue template.
