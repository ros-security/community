# ROS 2 Security Working Group Meeting Minutes
10 January 2023
[Meeting Recording](https://youtu.be/SZFmDwoYMN0) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-january-2022/23714)
 
## Agenda
- (Florencia) Approval requested: [Add minutes from meeting on December 13, 2022](https://github.com/ros-security/community/pull/44)
 
## Attendees
 
- Eduardo Ponz Segrelles (eProsima)
- Adam Mitz (Object Computing, Inc.)
- Ruffin White
- Gianluca Caiazza
- Roger Strain
- Florencia Cabral (Canonical)
 
## Administivia
 
### Approve last meeting minutes
 
[Minutes from the meeting on December 13, 2022](https://github.com/ros-security/community/pull/44) were approved.
 
## Discussion
 
* There was an update by Ruffin White on the [chain of trust issue](https://github.com/ros2/sros2/issues/282) with the single CA certificate in DDS, which was presented last meeting. This update builds on this [comment](https://github.com/ros2/sros2/issues/282#issuecomment-1377022381) added to the issue.
* A discussion followed that touched on the DDS implementations affected, implications and possible workarounds.
* There was an update by Eduardo Ponz Segrelles on [PKCS #11 support](https://github.com/ros2/design/pull/332). The developers revisited the design and opened a new PR addressing the comments on the original design, and also migrated some of the code on [RMW Fast RTPS](https://github.com/ros2/rmw_fastrtps/pull/565) to a PR for [RMW DDS Common](https://github.com/ros2/rmw_dds_common/pull/66), so other RMW implementations can leverage it.
* The group agreed to rework the tutorials for creating and deploying keystores on the ROS 2 documentation.

