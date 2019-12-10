# ROS 2 Security Working Group
The Security Working Group's mission is to advocate for and implement security features within ROS 2.  The working group negotiates a balance between benefits of security benefits and enabling technology, striving for a secure-by-default design which can be further customized to suit a system's security profile.

This document outlines the governance of the ROS 2 Security Working Group.  Updates to this document will be handled in the same manner as other project updates governed by the Working Group.

## Subprojects
A significant part of the Security Working Group's mission is achieved by maintaining ROS subprojects.  The following subprojects are owned by this Working Group:
 * _TBD:  Project name and team lead_

### Out of Scope
Although the following ROS subprojects have links to security, they are not governed by the Security Working Group:
 * _TBD_

### Adding New Subprojects
New subprojects must follow the following workflow to be added to the Security Working Group:
* Identify an existing Approver, a project lead and a sub-team to own the subproject (team size may be as small as one)
* Propose the new project to one or more Approvers
* The Approver creates a pull request
* The project lead must disuss the new subproject at the next Security Working Group meeting

### Maintaining Subprojects
Approved subprojects projects must these criteria:
* Build passes against ROS2 master
* The ROS2 standard linter set is enabled and adhered to
* Builds have 0 warnings
* Quality builds are green (address sanitizer, thread sanitizer, clang thread safety analysis)
* Test suite passes
* Reasonable* code coverage is met by test suites
* Issues are responded to promptly*
* Releases go out regularly* when bugfixes or new features are introduced

*-Precise definition of term not determined

### Vulnerability Handling
When a vulnerability has been identified in a subproject owned by the Security Working Group, the vulnerability will be triaged by one or more Approvers.

## Meetings
 * The working group typically meets on the second week of each month
 * Meetings are announced with the [wg-security tag](https://discourse.ros.org/tags/wg-security) on discourse.ros.org
 * Meeting notes are kept on the [ROS Wiki](http://wiki.ros.org/ROS2/WorkingGroups/Security)

## Governance


### Membership
The following is required to remain a member of the Security Working Group:
* _TBD_

### Roles
Security Working Group members may act in one or more of the following roles:
* Contributor
  * _TBD_
* Member
  * Attend at least 50% of the Security Working Group meetings
* Reviewer
  * _TBD_
* Approver
  * All approvers are also reviewers
  * Only approvers can create pull requests
* Moderator
  * _[This is Joe]_
