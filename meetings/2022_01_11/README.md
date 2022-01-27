# ROS 2 Security Working Group Meeting Minutes
 
11 January 2022
[Meeting Recording](https://www.youtube.com/watch?v=Bwqekv1dTZo) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-january-2022/23714)
 
## Agenda
- (Jeremie) Approval requested: Add minutes for meeting on December 14, 2021
- (Jeremie) Admin
   - Membership request: #25 #27 #30 #31 - no 'approver' applications
   - Template: #29
- (Jeremie) Explicit the mechanisms and rules for role downgrading: proposal review (gotta formalize that into a PR)
- (Jeremie) Discussion around reference implementation
 
## Attendees
Gianluca Caiazza
Marco Gutierrez
Victor Mayoral-Vilchez
Roger Strain
Ruffin White
Florencia Cabral
Cameron Mott
David Anthony
Jeremie Deray (artivis) | Canonical
Tomoya Fujita
 
## Administrivia
 
### Approve last meeting minutes
 
[Minutes from the meeting on December 14, 2021](https://github.com/ros-security/community/pull/32) were approved.
 
### Membership role changes and pull requests
 
- Accepted membership change requests [#25](https://github.com/ros-security/community/issues/25), [#27](https://github.com/ros-security/community/issues/27), [#30](https://github.com/ros-security/community/issues/30), and [#31](https://github.com/ros-security/community/issues/31). Ruffin White was added as Approver; Victor Mayoral-Vilchez was added as Reviewer; and Florencia Cabral was added as Member. Finally Mikael Arguedas was downgraded to Reviewer.
- Approved pull request [#29](https://github.com/ros-security/community/pull/29), with changes to the template for adding new projects to SWG. Victor will update request [#28](https://github.com/ros-security/community/issues/28) as per the new template.
 
### Mechanisms and rules for role downgrading
 
It was proposed to define a mechanism to formally downgrade Approvers, where inactive approvers will be downgraded to Member roles after 3 months of inactivity. Jeremie will formalize this proposal in a PR.
 
## SROS2 reference implementation
 
- Ruffin referenced existing demos for enabling SROS2 security on [a simulated Turtlebot3](https://github.com/ros-swg/turtlebot3_demo) and [on MoveIt2](https://github.com/ros-swg/moveit2_demo/tree/demo). Marco shared the [Robotic Middleware Framework (RMF)](https://github.com/open-rmf/rmf_demos/) demos, as interesting scenarios to consider, and Victor shared the [Robotics Capture the Flag](https://github.com/aliasrobotics/RCTF) project for reference.
 
- Jeremie opened the discussion around different aspects of the reference implementation:
   - objectives (ie, showcase the security features of ROS 2 in an actual platform, raise awareness around security, and improve the usability and documentation of SROS2);
   - platform to be used (Turtlebot4 was proposed as the upcoming reference ROS 2 robot);
   - target timeline (ROSCon 2022, possibly bringing it to a security-oriented venue, and to publicize in advance to generate interest); and
   - possible partnerships.
  
   Some concerns raised included the timeline for the availability of the Turtlebot4 robot; as an alternative the Turtlebot3 could be used. Different 'Capture the Flag' scenarios were discussed for the implementation. Next, Jeremie will share a document collecting these ideas for the group to continue collaborating on this project.

