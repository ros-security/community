# ROS 2 Security Working Group Meeting Minutes

09 Feb 2021 | [Meeting Recording](https://youtu.be/C75mfbKpClE) | [Meeting Announcement](https://discourse.ros.org/t/ros-2-security-working-group-meeting-09-feb-2021/18862)

## Agenda

 - Approve WG minutes for 1/26
 - (Ted) Progress update on `launch --secure`
 - Follow-up from demos (MoveIt, RMF)
 - Old business


## Attendees

Gianluca Caiazza,
[Iker Luengo Gil](https://github.com/IkerLuengo),
[Jacob Hassold](https://github.com/jhdcs),
[Jeremie Deray](https://github.com/artivis),
[Kyle Fazzari](https://github.com/kyrofa),
[Marco Gutierrez](https://github.com/marcoag),
Marques Rasmussen,
[Roger Strain](https://github.com/roger-strain),
[Ruffin White](https://github.com/ruffsl),
[Sid Faber](https://github.com/sidfaber)
[Ted Kern](https://github.com/arnatious)



## Discussion

[Meeting minutes for 1/26](https://github.com/ros-security/community/pull/14) were approved.


### Launch --secure

Instead of introducing the `--secure` option directly into ros launch (and also add dependency on nodl), the decision was made to create an extension system for ros launch which allows adding arbitrary flags and code. The plugin work is complete and a PR is proposed to support the new architecture.

[ros2/launch_ros PR #216](https://github.com/ros2/launch_ros/pull/216) can use a review, this adds the plugin extensibility to `ros2launch`.

Also [osrf/ros2launch_security PR #1](https://github.com/osrf/ros2launch_security/pull/1) needs reviews, this is the security extension implemented with the plugin architecture.

For reference, see the progression of how we got here with [ros2/launch_ros PR #180](https://github.com/ros2/launch_ros/pull/180), "add --secure option to launch with encryption".


### Follow up on demos

MoveIt! and RMF are both good candidates for instructing how to install `sros2` and to explore more advanced features.

Marco intends to continue implementing security in RMF. One focus of theres will be on certificate revocation, certificate authority hierarchies, and related features necessary for building third party trust.

Sid will continue discussing MoveIt security. This focus will be on establishing granular permissions in an existing ROS graph.

RMF and MoveIt are complimentary use cases. Marco and Sid will continue refining the goals and give an update at the next WG meeting.


### Old business

A brief discussion ensued regarding open quality issues (see below) and the [ROS vulnerability disclosure policy](https://ros.org/reps/rep-2006.html).


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

- 2020/09/22: [Test failures on test_security](https://github.com/ros2/system_tests/issues/435), [old version](https://github.com/ros2/system_tests/issues/446).
- 2020/06/09 (sid): Draft guidance for vendors on how to create a vulnerability disclosure policy. On hold pending external interest.
