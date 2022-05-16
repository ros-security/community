# ROS 2 Security Working Group Meeting Minutes
 
12 April 2022
[Meeting Recording](https://www.youtube.com/watch?v=C_3vnW8rQPA) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-march-2022/24528)
 
## Agenda
 
- (Jeremie) Approval requested: [Add minutes for meeting on March 08, 2022](https://github.com/ros-security/community/pull/37)
- Discussion around the recently published paper: SROS2: Usable Cyber Security Tools for ROS 2. Please read it in advance so we can have a good discussion. Some suggested discussion questions:
   - How can this work help promote usage and usability of SROS2? What's next?
   - How do you propose the framework or applied case study from this paper could be incorporated into our secured reference robot? Or contribute to other SWG projects?
   - One of the steps in the Devsecops framework is modeling/abstractions for using security, and during the last meeting it was mentioned leveraging NoDL for this aspect. Do you think there's some room for integrating NoDL with this framework?
 
## Attendees
 
Roger Strain
Kalle Koivisto
Ruffin White
Gianluca Caiazza
Victor Mayoral-Vilches
Jeremie Deray (artivis) | Canonical
Florencia Cabral | Canonical
 
## Administivia
 
### Approve last meeting minutes
 
[Minutes from the meeting on March 08, 2022](https://github.com/ros-security/community/pull/37) were approved.
 
## Paper discussion
 
- Discussion around the recently published paper: [SROS2: Usable Cyber Security Tools for ROS 2](https://aliasrobotics.com/files/SROS2.pdf). Some of the main issues discussed were:
   - Regarding this work's contribution to promoting usage and usability of SROS2:
       - It proposes a methodology for securing ROS 2 computational graphs
       - Mapping graphs accurately is at the core of adding security
   - Looking forward, some nice ideas include:
       - Graphical User Interfaces for the security process
       - Other communication middlewares (beyond DDS)
       - NoDL to assist in compiling proper representations of graphs
           - Challenges while extrapolating which interfaces are being used from the launch files
           - Mapping tooling can be understood as complementary
   - This work can be brought into the ROS 2 documentation, and promoted to the community via tutorials.
   - Need to convey a holistic approach to thinking about security as more than a series of tools; this systematic framework to showcase the maturity of ROS 2 security contributes to this goal.
   - Interest in bringing this work into a SWG project.