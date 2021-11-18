# ROS 2 Security Working Group Meeting Minutes
9 November 2021

[Meeting Recording](https://www.youtube.com/watch?v=52Sc-Q3IqWU) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-november-2021/22976)


## Agenda

(Jeremie) Approve WG meeting minutes for September 14, 2021
(David Anthony) Introduction and show-case
(Iker, Kalle) PKCS#11 update
(Víctor and related group) Guest talk about DDS Security research (link to [Black Hat talk] (https://www.blackhat.com/eu-21/briefings/schedule/index.html#the-data-distribution-service-dds-protocol-is-critical-lets-use-it-securely-24934))


## Attendees

Jeremie Deray | artivis (Canonical),
Víctor Mayoral-Vilches (Xilinx),
David Anthony (SwRI),
Florencia Cabral Berenfus (Canonical),
Gianluca Caiazza (Secura Factors),
Ruffin White (Secura Factors),
Iker Luengo Gil (eProsima)


## Administrivia

[Minutes from the meeting on September 14, 2021](https://github.com/ros-security/community/pull/23) were approved.


## ROS2 security usability

David Anthony (SwRI) shared about their interest and challenges in using security with ROS 2, and trying to introduce security practices into their development workflow.

[Link to the slides](2021-011-SwRI-ROS2SecurityWGpresentation.pdf)

Some of their challenges in this process are: integrating security into the development workflow; working with command line tools in complex systems; and verifying that the system is properly configured after applying SROS2 tools. Some specific challenges are listed in Slide 5 of the PPT presentation.

Some suggestions for improvement (Slide 6) are:
- Having graphical tools for configuring and inspecting encryption, governance and policy settings (possibly using rqt graph to visualize which topics are encrypted; which keys are used for encryption, etc)
- Better integration into CI/CD pipeline and deployment: be able to set configuration options programmatically
Node introspection: possibility of node info or rostopic info show information on the enclaves a node is using/how publishers/subscribers are configured for encryption
- Efficient key management for their large UAV swarm

### Feedback from other meeting participants:

- Agreement that security features are there, but usability can be improved
- Suggestion to look into the [‘ros2 launch security’](https://github.com/osrf/ros2launch_security)] effort, still under development
- The way forward might require defining a security reference system based on a common use case.
    - Consider following the example of other working groups such as real time, [here](https://github.com/ros-realtime/reference-system), and past reference examples used in the SWG, such as the [Secure Turtlebot3 Demo](https://github.com/ros-swg/turtlebot3_demo) and [ROS2 Security Workshop at RosCon 2019](https://ros-swg.github.io/ROSCon19_Security_Workshop/)


### PKCS#11 Update

- There is a [pull request](https://github.com/ros2/rmw_fastrtps/pull/565) for adding support for PKCS#11
- There is a [pull request](https://github.com/eProsima/Fast-DDS/pull/2222) to add in FastDDS
- A showcase could be shared with the SWG by January


### DDS security

- There will be a [talk at the Black Hat Europe conference](https://www.blackhat.com/eu-21/briefings/schedule/index.html#the-data-distribution-service-dds-protocol-is-critical-lets-use-it-securely-24934) on Nov. 11, presenting some critical DDS security vulnerabilities that were found
- Will look to arrange a brief about this for the SWG in the near future
- Shared a scapy layer that implements a dissect of RTPS: https://github.com/secdev/scapy/pull/3403


## TODO

Set up shared document to collectively work on defining a reference security demo (Jeremie)
