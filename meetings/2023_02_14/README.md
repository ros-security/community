# ROS 2 Security Working Group Meeting Minutes
14 February 2023
[Meeting Recording](https://youtu.be/nOo80kP_I4E) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-february-2023/29675)
 
## Agenda
- (Florencia) Approval requested: [Add minutes from meeting on January 10, 2023](https://github.com/ros-security/community/pull/45)
 
## Attendees
 
- Florencia Cabral (Canonical)
- Ruffin White
- Gianluca Caiazza
- Esteban Martinena Guerrero
- Kalle Koivisto (Unikie / TII SSRC)
- Eduardo Ponz Segrelles(eProsima)
- Patrick Dahlke (Apex.AI)
- Mikael Arguedas
 
## Administivia
 
### Approve last meeting minutes
 
[Minutes from last meeting on January 10, 2023](https://github.com/ros-security/community/pull/45) were approved.
 
## Discussion

* The group had a discussion around code scanning tools and security assurance for ROS projects. Some issues addressed were the status of integrations for ROS, challenges for ROS developers to use them in CI/CD workflows, and any development or documentation needed in that direction. A [request for community input](https://discourse.ros.org/t/inquiry-about-use-of-security-code-scanning-in-ros-projects/29713) was shared before this meeting to incorporate feedback from the community.
* As agreed in the last meeting, a [PR was opened](https://github.com/ros2/ros2_documentation/pull/3318) for expanding the tutorials in the ROS 2 documentation on creating and deploying SROS2 keystores. Some of the feedback provided by the group included possibly adding a `deploy enclave` verb or another such mechanism to ease key deployment.
* There was an update on PKCS #11 design and related PRs, and feedback from the group:
    - ros2/design: [ROS2 DDS Security PKCS#11 URI support #332](https://github.com/ros2/design/pull/332)
    - ros2/rmw_fastrtps: [Add support for PKCS#11 in security files](https://github.com/ros2/rmw_fastrtps/pull/565)
    - ros2/rmw_dds_common: [Add pkcs11 support to get_security_files](https://github.com/ros2/rmw_dds_common/pull/66)
* Update on the chain of trust security vulnerability on DDS, as discussed in previous meetings. There is now a [proposed fix on Fast DDS](https://github.com/eProsima/Fast-DDS/pull/3294). 
