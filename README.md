# ROS 2 Security Working Group
The Security Working Group's mission is to advocate for and implement security features within ROS 2.  The working group negotiates a balance between the benefits of and the enablement of technology, striving for a secure-by-default design which can be customized to suit a targeted security profile.

This document outlines the governance of the ROS 2 Security Working Group.  Updates to this document will be handled in the same manner as other project updates governed by the Working Group.

## Subprojects
A significant portion of the Security Working Group's mission is achieved by maintaining ROS subprojects.  The following subprojects are owned by this Working Group:
 * _TBD:  list project names and team leads_

### Out of Scope
Although the following ROS subprojects have links to security, they are not governed by the Security Working Group:
 * _TBD_

### Adding New Subprojects
New subprojects must follow the following workflow to be added to the Security Working Group:
* Identify a subproject lead and a sub-team to own the subproject.  Single-person subproject teams are allowed.
* Work with an Approver to scope the project and create a pull request.
* The subproject lead must introduce the new subproject at the next Security Working Group meeting; the pull request may or may not be queued until the meeting.

### Maintaining Subprojects
Approved subprojects must these criteria:
* Build passes against ROS2 master
* The ROS2 standard linter set is enabled and adhered to
* Builds have 0 warnings
* Quality builds are green (address sanitizer, thread sanitizer, clang thread safety analysis)
* Test suite passes
* Reasonable* code coverage is met by test suites
* Issues are responded to promptly*
* Releases go out regularly* when bugfixes or new features are introduced

_*-Precise definition of term not determined_

## Vulnerability Handling
The Security Working Group is responsible for handling vulnerability reports filed against ROS.  Until a more comprehensive vulnerability handling program is established, the Working Group will perform the following:
* Maintain a publicly accessible email address for securely reporting vulnerability details.
* A Reviewer will triage reported vulnerabilities within a reasonable time and assign the vulnerability to a work queue
* As part of the triage, the reviewer will propose a [CVSS Base Score](https://www.first.org/cvss/calculator/3.1) for the vulnerability
* For high risk vulnerabilities (CVSS score 9.0 and above), the Reivewer will track remediation progress.
* For high risk vulnerabilities, the Working Group Moderator will work with the broader ROS community to communicate when the patch is released and the potential impact.

## Governance
This guidelines are designed exclusively to help the Working Group achieve its mission, but are subject to change should they become cumbersome or ineffective.

### Meetings
 * The working group typically meets on the second week of each month
 * Meetings are announced on discourse.ros.org using the [wg-security tag](https://discourse.ros.org/tags/wg-security)
 * Meeting notes are kept on the [ROS Wiki](http://wiki.ros.org/ROS2/WorkingGroups/Security)

### Roles
Security Working Group members may act in one or more of the following roles:
* __Contributor__:  A person contributing code to the Security Working Group subprojects
  * Timely response to comments
  * Contribute code to one or more subprojects
* __Member__:  A participant in Security Working Group discussions.  Responsiblities include:
  * Attending a majority of the Security Working Group meetings
  * Commenting on pull requests
  * Any Approver may invite new Member to join the Working Group
  * New members should be recognized at the next Security Working Group meeting
* __Reviewer__:  Responsible for reviewing pull requests
  * _TBD_
  * Triage vulnerability reports
* __Approver__:  Responsible for approving pull requests
  * All approvers are also reviewers
  * Only approvers can create pull requests
* __Moderator__:  Responsible for facilitating the governance structure.
  * Granting and removing access
  * Schedule Working Group meetings
  * Ensure someone from the Security WG attends the ROS TSG
  * Although a single person normally acts as Moderator, at least one alternate individual must be assigned Moderator rights.
