# ROS 2 Security Working Group
The Security Working Group's mission is to advocate for and implement security features within ROS 2.  The working group negotiates a balance between the benefits of security and the enablement of technology, striving for a secure-by-default design which can be customized to suit a targeted security profile.

This document outlines the governance of the ROS 2 Security Working Group.  Updates to this document will be handled in the same manner as other project updates governed by the Working Group.

## Subprojects
A significant portion of the Security Working Group's mission is achieved by maintaining ROS subprojects.  The following subprojects are owned by this Working Group:
 * _TBD:  list project names and team leads_

### Out of Scope
Although the following ROS subprojects have links to security, they are not governed by the Security Working Group:
 * _TBD_

### Adding and Maintaining Subprojects
Subprojects must meet the following criteria:
* An Approver can add or create a new subproject that will be maintained by this working group.
* A Member should introduce new subprojects at the next Security Working Group meeting
* Builds must pass against ROS2 master
* The ROS2 standard linter set must be enabled and adhered to
* Builds must have 0 warnings
* Quality builds must be green (address sanitizer, thread sanitizer, clang thread safety analysis)
* Test suite must pass
* Reasonable* code coverage must be met by test suites
* Issues must be responded to promptly*
* Releases must go out regularly* when bugfixes or new features are introduced

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
  * Timely response to comments.
  * Contribute code to one or more subprojects.
  * Contributors do not need to particpate in the Working Group beyond contributing code.
* __Member__:  A participant in Security Working Group discussions.  Responsiblities include:
  * Attending a majority of the Security Working Group meetings
  * New members should be recognized at the next Security Working Group meeting
* __Reviewer__:  Responsible for reviewing pull requests
  * Review and comment on pull requests
  * Triage vulnerability reports
* __Approver__:  Responsible for approving pull requests
  * All approvers are also reviewers
  * Approvers can add members to the Working Group
  * Only approvers can create pull requests
* __Moderator__:  Responsible for facilitating the governance structure.
  * Granting and removing access
  * Schedule Working Group meetings
  * Ensure someone from the Security WG attends the ROS TSG
  * Although a single person normally acts as Moderator, at least one alternate individual must be assigned Moderator rights.
