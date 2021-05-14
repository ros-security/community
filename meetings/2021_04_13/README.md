# ROS 2 Security Working Group Meeting Minutes
13 Apr 2021

[Meeting Recording](https://youtu.be/6FBraGphxcI) | [Meeting Announcement](https://matrix.to/#/!LcRLnAIRWjSCfZmMeD:matrix.org/$debdyjMNrch_edOWmavhC9CckFfXqBg4mwr2-5y9fvQ?via=matrix.org)


## Agenda

 - Approve: [Add meeting minutes for March 9, 2021](https://github.com/ros-security/community/pull/17)
 - Upcoming Foxy sync, [Galactic feature freeze](https://discourse.ros.org/t/galactic-api-and-feature-freeze-in-rolling/19795) on 4/19 
 - Security logging in Fast-DDS, quick update
 - Old business

## Attendees

Gianluca Caiazza,
[Iker Luengo Gil](https://github.com/IkerLuengo),
[Jacob Hassold](https://github.com/jhdcs),
[Jeremie Deray](https://github.com/artivis),
[Roger Strain](https://github.com/roger-strain),
[Ruffin White](https://github.com/ruffsl),
[Sid Faber](https://github.com/sidfaber)


## Administrivia

[Minutes from the meeting on March 9, 2021](https://github.com/ros-security/community/pull/17) were approved.

## Galactic Feature Freeze

Recent merge from Mikael updated to the latest version; nothing else significant seems to be pending.


## Security Logging

The security logging plugin has already landed in FastDDS (FastRTPS), it gives the ability to log to a text file. However, the DDS spec also allows logging directly to the DDS graph. This is current work-in-progress.

[Watch the demo](https://youtu.be/6FBraGphxcI?t=289)

Part of this work proposes permissions for the logging readers and logging writers. Nodes should have write access to the log node automatically when logging is enabled.

Additionally the security logging topic has some characters (semicolons) that ros does not recognize. Should the ros2 logging node be neede within the ROS graph, a bridge node may be required. However, the topic can remain invisible to the graph when not needed in ROS and used to log directly to syslog or another destination.


## Test update

[FastRTPS issue 522](https://github.com/ros2/rmw_fastrtps/issues/522) and [ros2 PR 1114](https://github.com/ros2/ros2/pull/1114) addressed a fastdds problem that created a regresson for multiple subscribers on a single topic. This issue should be fixed with the latest release, and the ROS2 team is working on a backport to foxy. However, an sros2 issue should be created to add tests with multiple readers and multiple writers.

***See [sros2 issue 261](https://github.com/ros2/sros2/issues/261)***




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
