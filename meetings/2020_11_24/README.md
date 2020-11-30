# ROS 2 Security Working Group Meeting Minutes
24 Nov 2020

[Meeting Recording](https://youtu.be/7ZJidRtTqXI) | [Meeting Announcement](https://discourse.ros.org/t/security-wg-meeting/17519)


## Agenda

- Administrivia: future meeting minutes
- G-turtle goals
  - MoveIt2 security use case
  - ROS 2 without a file system, [rcl #545](https://github.com/ros2/rcl/issues/545) and [discourse post](https://discourse.ros.org/t/ros-2-without-a-file-system/16942)
  - [Galactic Roadmap](https://index.ros.org/doc/ros2/Roadmap/#id2) 
  - sros2 quality status: any comments?
- ROS2 secure launch and access control
- [RMF](https://osrf.github.io/ros2multirobotbook) as a use case, see the [demo](https://github.com/osrf/rmf_demos)
- Revoking keys

## Attendees
[Iker Luengo Gil](https://github.com/IkerLuengo),
[Jacob Hassold](https://github.com/jhdcs),
[Jaime Martin Losa](https://github.com/JaimeMartin),
[Jeremie Deray](https://github.com/artivis),
[Kyle Fazzari](https://github.com/kyrofa),
[Marco Gutierrez](https://github.com/marcoag),
[Mikael Arguedas](https://github.com/mikaelarguedas),
[Ruffin White](https://github.com/ruffsl),
[Sid Faber](https://github.com/sidfaber)


## Administrivia

Following a brief discussion, it was decided to move new meeting minutes to the [`ros-security/community` Github reposityr](https://github.com/ros-security/community). Existing meeting minutes in the [ROS wiki](http://wiki.ros.org/ROS2/WorkingGroups/Security) will not be ported.

The [vulnerability remediation procedure PR](https://github.com/ros-security/community/pull/8) is still open for comments.


## G-Turtle goals

Five open items could become part of our G-Turtle deliverables:

### Reference implementation with MoveIt

Goal would be to demonstrate "Hey, look, here's an example of a real system that's secured." Although the config may be able to stand on its own, it would be more useful as an example.
This example will also be useful for us to find issues with the security implementation on a complex system to test: CPU / network utilization, what to sign, what to encrypt, overall impact to the system.
This also becomes a proving ground for NoDL.

Use this implementation to configure security levels per topic, following the ones supported by DDS-Security: NONE, SIGN, ENCRYPT. Currently SROS2 is all or nothing, either all topics are encrypted or no security feature is used at all. See [Tracking ticket #130, "Provide some granularity for individual topic protection"](https://github.com/ros2/sros2/issues/130).

Simulation may be challenging; a simulated implementation may not quite match the real world implementation. However, we should be able to spec the project in stages. Start simple and build upon the demo.

### Enable DDS security without a file system

The scope of this issue is much wider than just security. Success depends upon buy-in from both the micro-ROS community and from Open Robotics.

The WG agrees to continue to move the discussion forward to flesh out a design, but not to perform any work on the code at this time.

### [sros2 quality](https://github.com/ros2/sros2/issues/217)

Even though a quality upgrade is stalled on dependent package quality levels, we should continue working on improving sros2 quality. The most important work is to improve documentation.

Currently sros2 users aren't using online resources, and they need more / better documentation. The recommended path forward is to add a full section on security to the ROS 2 tutorials. This should build on the examples of the existing tutorials, and demonstrate how to re-do them with security enabled.

A discussion also ensued on the current status of [answers.ros.org](https://answers.ros.org/questions/).

### Permissions file size

Mikael has been working on uglifying the permissions files. Work on this continues.

### Integration test failures

Mikael described the current state of [failures in test_security](https://github.com/ros2/system_tests/issues/446). The WG agreed that these tests should be fixed, although no specific action items were identified.

### Conclusion
The WG will focus on the following primary items for G-turtle:

- A reference implementation of security
- Improving sros2 quality through documentation updates

The WG will also continue working on the following items:

- Design input for running ROS without a file system
- Reducing permission file size / complexity
- Fixing test failures

## Open Discussion
ROS launch status: the initial launch is working but does not include access control. The work is in progress, but stalled pending discussions on [launch_ros PR 180](https://github.com/ros2/launch_ros/pull/180). Some comments are suggesting a plugin solution, which would change future PRs.

Marco suggested [the Robotics Middleware Framework (RMF)](https://github.com/osrf/rmf_demos) as a reference implementation for ROS security. This should be ready to run with ROS 2; they have already done some work with security as well.

Marco also asked about revoking keys: there's a need to handle that within RMF should an individual robot in a fleet be physically compromised. Jaime provided [information on CRLs from eProsima](https://fast-dds.docs.eprosima.com/en/latest/fastdds/security/auth_plugin/auth_plugin.html#generating-the-certificate-revocation-list-crl).

## References
More information about items that were discussed:
- [Vulnerability remediation procedure PR](https://github.com/ros-security/community/pull/8)
- [sros2 quality](https://github.com/ros2/sros2/issues/217)
- [Failures in test_security](https://github.com/ros2/system_tests/issues/446)
- [Secure launch_ros PR 180](https://github.com/ros2/launch_ros/pull/180)
- [The Robotics Middleware Framework (RMF)](https://github.com/osrf/rmf_demos)
- [RMF: Programming multiple robots with ROS 2](https://osrf.github.io/ros2multirobotbook/)
- [FastDDS and CRLs](https://fast-dds.docs.eprosima.com/en/latest/fastdds/security/auth_plugin/auth_plugin.html#generating-the-certificate-revocation-list-crl)

## Open action items

- 2020/09/22: [Test failures on test_security](https://github.com/ros2/system_tests/issues/446)
- 2020/06/09 (sid): Draft guidance for vendors on how to create a vulnerability disclosure policy.

Closing the following items as this work is actively in progress:

- 2020/09/22: Kyle/Mikael to add an issue for uglifying permissions files
- 2020/07/28: Mikael and Ruffin to try and shave size off the perm files and wildcard to optimize, then push upstream. Follow up with a discussion on matrix. See https://github.com/ros-swg/turtlebot3_demo/pull/34#issuecomment-665439493.
- 2020/05/12: Review [Move security related filesystem and env utilities outside rcl · Issue #545 · ros2/rcl](https://github.com/ros2/rcl/issues/545) and comment
