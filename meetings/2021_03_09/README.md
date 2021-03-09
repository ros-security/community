# ROS 2 Security Working Group Meeting Minutes
09 Mar 2021

[Meeting Recording](https://youtu.be/iYObjFJITtU) | [Meeting Announcement](https://app.element.io/?pk_vid=16062276209ae8cc#/room/!LcRLnAIRWjSCfZmMeD:matrix.org)

## Agenda

- Approve [PR #16: Add minutes for meeting on 23 Feb 2021](https://github.com/ros-security/community/pull/16/files)
- (ruffin) [Broken TB3 demo](https://github.com/rticommunity/rmw_connextdds/issues/8)
- (All) [Foxy Regression](https://github.com/ros2/sros2/issues/252) recap
- (Sid) ROS2 security with an external CA


## Attendees

Gianluca Caiazza,
[Jacob Hassold](https://github.com/jhdcs),
[Marco Gutierrez](https://github.com/marcoag),
Phil Wolff,
[Roger Strain](https://github.com/roger-strain),
[Ruffin White](https://github.com/ruffsl),
[Sid Faber](https://github.com/sidfaber)


## Administrivia

[Meeting minutes for meeting on 23 Feb 2021](https://github.com/ros-security/community/pull/16/files) were approved.

Members agreed to shift the working group meetings to monthly, 45 minutes long.


## [Broken TB3 demo](https://github.com/rticommunity/rmw_connextdds/issues/8)

While revisiting a more complex example, the Foxy Regression was identified. After that was fixed, moved ahead with a more complex implementation with many nodes and many topics. The cyclone `fastrtps` security plugins work. `rmwconnect_cpp` did not working even without security enabled. RTI v6 connextdds implementation works both with and without security with ACLs disabled. Encryption was working.

Currently the default rmw is no longer working even without access controls nor encryptions. It only works without security. Also although the toy demos are working, it does not work well at scale. Need to continue investigating how to improve testing to cover scaling.

Main lesson learned from the [Foxy Regression](https://github.com/ros2/sros2/issues/252) recap is to improve unit testing to detect this type of failure, but recognize that unit tests still won't cover everything.


## ROS2 security with an external CA

Sid discussed the MoveIt use case status:
 - two identical LXD images, able to separate duties: one robot container, one monitor container. Have a test launch that moves the arm (not supposed to work on the monitor node)
 - Able to enable security on the robot container, and transfer the security artifacts to the monitor container to secure the robot. Also able to create separate security artifacts for the monitor container.
 - All done using an offboard CA.

Discussed some questions about the status of the current use case. Full iteration on the details will likely happen in a PR to update ROS documentation.

- Is an offboard CA using LXD + openssl a good use case to document? Yes. It should grow into dealing with multiple, external CAs, even a cahin of CAs and how to use them with ROS.

- Optimize the setup within reason to keep certificate size to a minimum.

- Keep the revocation use case as a separate but important issue.

- The initial root CA policy can include default certificate signature length of one year, default root CA lifetime of 10 years, trimming attributes other than the certificate common name. However, see [`keyserver_config.yaml`](https://github.com/ros/ros_comm/blob/sros/tools/sros/conf/keyserver_config.yaml) for a discussion on which extended attributes should be set.

- It's acceptible to use the same CA for both identity and permissions. The use case for separating them is rare.


This can also map to the [Distributed Identity Foundation](https://identity.foundation/?) model for creating distributed trust. This builds on the CA model. This may be a nice alternative to the traditional CA model, and could enable components within ROS to trust each other.


## References

The following links were shared during the presentation:

- [Terminate called after throwing an instance of 'rclcpp::exceptions::RCLError' with Nav2 #8](https://github.com/rticommunity/rmw_connextdds/issues/8)
- [HowTo: Create a ROS CA](https://docs.google.com/document/d/1xvJZp9Sr3KpVZuoRGVsCsoApzrh-hj3C6gz57B68Euc/edit)
- [ros_comm/tools/sros/conf/keyserver_config.yaml](https://github.com/ros/ros_comm/blob/sros/tools/sros/conf/keyserver_config.yaml)
- [The Distributed Identity Foundation](https://identity.foundation/)
- [ROS Security WG Breakout Meeting | Invited Talk on Privaros](https://discourse.ros.org/t/ros-security-wg-breakout-meeting-invited-talk-on-privaros/17848)


---

## Open sros2 quality issues
[sros2 package Quality level status #217](https://github.com/ros2/sros2/issues/217)

 - Version
   - 1.ii: at a stable version (e.g. for semver that means version >= 1.0.0)
 - Change control
   - 2.v: documentation policy for all change requests
 - Documentation
   - 3.i: documentation for each "feature"
   - 3.ii: documentation for each item in the public API
   - 3.v: a "quality declaration" document
 - Testing
   - 4.i: system tests which cover all items in the "feature" documentation
   - 4.ii: system, integration, and/or unit tests which cover all of the public API
   - 4.iv.a: performance tests
   - 4.iv.b: a performance regression policy
 - Dependencies
   - 5.i: no direct runtime "ROS" dependencies which are not at the same level
   - 5.ii: no optional direct runtime "ROS" dependencies which are not 'Level N'
   - 5.iii: justification for why each direct runtime "non-ROS" dependency is equivalent to a 'Level N' package in terms of quality

---

## Open action items

- 2020/09/22: [Test failures on test_security](https://github.com/ros2/system_tests/issues/446)
- 2020/06/09 (sid): Draft guidance for vendors on how to create a vulnerability disclosure policy.
