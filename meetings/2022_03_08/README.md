# ROS 2 Security Working Group Meeting Minutes
08 March 2022
[Meeting Recording](https://www.youtube.com/watch?v=C_3vnW8rQPA) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-march-2022/24528)
 
## Agenda
 
- (Jeremie) Approval requested: [Add minutes for meeting on February 08, 2022](https://github.com/ros-security/community/pull/36)
- (Florencia) Presentation "NoDL and its relation to sros2"
 
## Attendees
 
Tomoya Fujita - Sony
Gianluca Caiazza
Guillaume Beuzeboc
Roger Strain
Marco Gutierrez
Victor Mayoral-Vilches | Alias Robotics
Jeremie Deray (artivis) | Canonical
Florencia Cabral | Canonical
 
## Administivia
 
### Approve last meeting minutes
 
[Minutes from the meeting on February 08, 2022](https://github.com/ros-security/community/pull/36) were approved.
 
## NoDL Presentation
 
- Florencia presented [the NoDL project](https://github.com/ubuntu-robotics/nodl), including its technical description, usage, future directions, and packages currently using it, such as [ros2launch_security](https://github.com/osrf/ros2launch_security) and [nodl_to_policy](https://github.com/aprotyas/nodl_to_policy).
- The presentation slides are available [here](NoDL_ Presentation_SWG_Mar08.pdf)
- There was a follow-up discussion about this package's features, limitations and future work. Some points discussed related to using NoDL for third party nodes; assessing security policies generated from NoDL; and [HAROS](https://github.com/git-afsantos/haros) as a complementary project that introduces the ability to do static graph introspection.
- Action points for future meetings included inviting the HAROS maintainers for a discussion, and taking advantage of synergies with academic work being done by other SWG members related to modeling ROS 2 computational graphs.