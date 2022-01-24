# ROS 2 Security Working Group Meeting Minutes
 
14 December 2021
 
[Meeting Recording](https://www.youtube.com/watch?v=SZXOOYDsjxc&feature=youtu.be) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-december-2021/23399)
 
 
## Agenda
 
 
(Jeremie) Approval requested: Add minutes for meeting on November 9, 2021
(Jeremie) Re-populate the WG with a group of individuals who can jointly manage the group.
(Jeremie) Explicit the mechanisms and rules for role downgrading: The roles of the working group participants are explicitly defined together with the rules to upgrade said roles (see [here](https://github.com/ros-security/community#roles)). However, there are no explicit rules to downgrade roles, especially in the case of clear inactivity.
(Jeremie) Call for action: cleanup sros2 issues/PRs. Starting with #275, #29.
(Victor) Guest talk about DDS Security research
(Jeremie - if time allows) Discussion around reference implementation
 
 
## Attendees
 
Jeremie Deray,
Kalle Koivisto,
Christian R.,
Florencia Cabral,
Ruffin White,
Shaun Murphy,
Werner Burger,
Florian Tax,
Gianluca Caiazza,
Victor Mayoral-Vilchez
 
 
## Administrivia
 
[Minutes from the meeting on November 9, 2021](https://github.com/ros-security/community/pull/24) were approved.
 
 
## Group membership and roles
 
### Approving member roles
 
The group requires active members with roles as Reviewers and Approvers, and currently they are very limited.
 
Some pending membership requests:
- [Victor's request](https://github.com/ros-security/community/issues/25) is waiting for inactive approvers
- [Florencia's request](https://github.com/ros-security/community/issues/27) is waiting for some changes in the rules
- Ruffin should apply for Approver role
 
Jeremie will add the official list of members to the community repo once it is updated.
 
### Role downgrading
 
Currently, the group doesn't have explicit mechanisms and rules for role downgrading, and this is necessary, especially in the case of clear inactivity. It was agreed that a mechanism for downgrading members will be proposed at the next WG meeting.
 
## Open issues/PRs
 
There are some sros2 issues and PRs pending review (i.e., [#275](https://github.com/ros2/sros2/issues/275), [#29](https://github.com/ros2/sros2/pull/29)).
Members most familiar with them will work on these reviews; Victor will look at #275.
 
## DDS security research
 
- Victor Mayoral-Vilchez gave a guest talk to present his research group's findings on Data Distribution Service (DDS) security vulnerabilities. These were first presented at the [Black Hat Europe conference 2021](https://www.blackhat.com/eu-21/briefings/schedule/index.html#the-data-distribution-service-dds-protocol-is-critical-lets-use-it-securely-24934) last November 11, and a similar talk to this was given at the [ROS Industrial Europe Conference](https://rosindustrial.org/events/2021/12/1/ros-industrial-conference-2021) on December 2. The results of the research were also shared on [ROS Discourse](https://discourse.ros.org/t/cybersecurity-in-the-ros-2-communication-middleware-targeting-the-top-6-dds-implementations/23254). He touched on the methodology used for this research, which included a dissector of ROS2 layers crafted by the team, which was used to analyze RTPS (DDS's underlying networking protocol). The findings included several vulnerabilities such as a network reflection/amplification vulnerability affecting the DDS protocol, and configuration-based vulnerabilities on several implementations. Finally, Victor shared demos of the POCs for these issues.
 
- Victor also shared a personal project, the ["Robot Hacking Manual"](https://github.com/vmayoral/robot_hacking_manual), which includes case studies and tutorials that aim to raise awareness of and discuss tools for robotics cybersecurity, using a security-first approach.
 

