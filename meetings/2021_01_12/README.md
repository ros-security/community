# ROS 2 Security Working Group Meeting Minutes
24 Nov 2020

[Meeting Recording](https://youtu.be/drn4nOHS7BM) | [Meeting Announcement](https://discourse.ros.org/t/moveit-2-demo/18307)

## Agenda

- Approve meeting minutes from last meeting
- MoveIt 2 demo, Henning Kayser, MoveIt 2 Development Lead

## Attendees
Gianluca Caiazza,
Hamal Marino,
[Iker Luengo Gil](https://github.com/IkerLuengo),
[Jacob Hassold](https://github.com/jhdcs),
[Jaime Martin Losa](https://github.com/JaimeMartin),
[Jeremie Deray](https://github.com/artivis),
[Kyle Fazzari](https://github.com/kyrofa),
[Marco Gutierrez](https://github.com/marcoag),
Marq Rasmussen,
[Mikael Arguedas](https://github.com/mikaelarguedas),
[Roger Strain](https://github.com/roger-strain),
[Ruffin White](https://github.com/ruffsl),
[Sid Faber](https://github.com/sidfaber),
[Ted Kern](https://github.com/arnatious)


## Administrivia

Approve the [minutes from the meeting on 15 Dec 2020](https://github.com/ros-security/community/pull/10)

Next meeting is on January 26, 3 hours earlier, it will be a demo of RMF by Marco.


## MoveIt 2 Demo

[Slides](SecuringMoveIt2.pdf) | [Web site](https://moveit.ros.org/) | [github](https://github.com/ros-planning/moveit2)

Discussion outline:
 - [00:00](https://youtu.be/drn4nOHS7BM) Intro
 - [01:49](https://youtu.be/drn4nOHS7BM?t=109) Features and Interfaces: MoveGroup
 - [07:17](https://youtu.be/drn4nOHS7BM?t=437) Features and Interfaces: MoveItCpp API
 - [08:12](https://youtu.be/drn4nOHS7BM?t=492) Features and Interfaces: MoveIt Servo
 - [08:58](https://youtu.be/drn4nOHS7BM?t=538) MoveGroup use case and ROS vulnerabilities
 - [11:15](https://youtu.be/drn4nOHS7BM?t=675) Hardware security
 - [13:52](https://youtu.be/drn4nOHS7BM?t=832) What is the motivation for security in MoveIt?
 - [19:35](https://youtu.be/drn4nOHS7BM?t=995) An overview of SROS2 and what it enables: encryption for privacy, message integrity checking
 - [27:35](https://youtu.be/drn4nOHS7BM?t=1665) How NoDL fits in with security by automatically generating security artifacts
 - [32:45](https://youtu.be/drn4nOHS7BM?t=2145) Logging considerations 
 - [35:40](https://youtu.be/drn4nOHS7BM?t=2140) A use case for using certificates to separate hardware code from consumer code
 - [39:33](https://youtu.be/drn4nOHS7BM?t=2373) Getting started simulating MoveIt 2; exploring how to secure a remote rviz instance
 - [45:36](https://youtu.be/drn4nOHS7BM?t=2736) Exploring the size of the ros graph generated with the MoveGroup demo
 - [51:11](https://youtu.be/drn4nOHS7BM?t=3071) Handling security failures in the proposed rviz use case
 

## References

The following links were shared during the presentation:

 - https://github.com/ros-planning/moveit2/blob/main/moveit_ros/moveit_servo/doc/servo_tutorial.md
 - https://docs.google.com/presentation/d/1me_0kQZtZw7tZnrSGmVtdYv8eTcAbGjCNhTpgG8uIR4/edit#slide=id.p
 - https://github.com/ros-planning/moveit2/tree/main/moveit_demo_nodes


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
