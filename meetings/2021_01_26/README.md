# ROS 2 Security Working Group Meeting Minutes
26 Jan 2021

[Meeting Recording](https://youtu.be/jWBJVDxFPfo) | [Meeting Announcement](https://discourse.ros.org/t/robotics-middleware-framework-rmf-demo/18531)

## Agenda

- Approve [meeting minutes from last meeting](https://github.com/ros-security/community/pull/11)
- MoveIt 2 demo follow-up
- RMF Demo, [Marco Gutierrez](https://github.com/marcoag)

## Attendees
Gianluca Caiazza,
[Iker Luengo Gil](https://github.com/IkerLuengo),
[Jacob Hassold](https://github.com/jhdcs),
[Jaime Martin Losa](https://github.com/JaimeMartin),
[Jeremie Deray](https://github.com/artivis),
Kalle Koivisto,
[Marco Gutierrez](https://github.com/marcoag),
[Mikael Arguedas](https://github.com/mikaelarguedas),
Paul Verhoeckx,
Ramon Wijnands
[Roger Strain](https://github.com/roger-strain),
Rokus Ottervanger,
[Ruffin White](https://github.com/ruffsl),
[Sid Faber](https://github.com/sidfaber),
Tianshi Xiang

## Administrivia

- No comments on meeting minutes
- No additional action items from the MoveIt demo


## RMF Demonstration

### Introduction to RMF
- 2:20 Intro - Marco works for OR in Singapore on Robotics Middleware Framework, including releases and exploring security

- 5:01 (slide 4) - RMF is about multi-robot systems. Challenges include:
  - Interoperabilities
  - Testing 
  - Infrastructure
  - Security

- 7:03 (slide 7) - What RMF can do: it interacts with doors and lifts, handle test planning and allocation, fleet traffic, management and workcell interaction

- 8:07 (slide 11) - The core system takes care of allocation tasks, traffic management, etc. Adapters can connect to different parts of the infrastructure.

- 9:32 (slide 12) - RMF simplifies / standardizes messages. It is a system of systems synthesizer, allowing different systems to talk in different protocols; plugins translate between protocols. Also provides standard messages.

- 10:32 (slide 13) - Different robots allow different amounts of control.

- 15:30 (slide 16) - RMF can resolve unexpected conflicts in a dynamic envionment.

- 18:26 (slide 22) - The RMF toolbox
  - Traffic editor: annotate floor plans
  - Building map tools
  - Testing; able to use [Ignition Robotics](https://app.ignitionrobotics.org/fuel) models
  - rmf_core provides integration with rmf

- 20:30 (slide 28) - RMF includes [UI signalling](https://github.com/osrf/soss)

- 21:00 (slide 29) - Use the operations dashboard for monitoring schedules and trajectories. The dashboard is migrating from rviz (foxy release) to web-based (build from source).

### Demonstration

- 23:26 See the rmf-demos repository. Four demos: office, airport, clinic, hotel. Also a [multi-robot book](https://osrf.github.io/ros2multirobotbook) to help get started. Begin with the office demo, simplest of the group. You can submit deliveries or loops through the web interface or through gazebo. Also can submit a list of tasks, can be loaded from a .json file.

- 29:35 (slide 32) - Security challenges. Most significant and difficult problem is dealing with third party hardware and software.

### Q&A

- 32:05 Any questions on how security works? what you get with sros2?

- 33:25 Can you expand on the human component of your security concerns?

- 43:40 How do you define trust boundaries, set up your certificate hierarchy?

- 46:50 Integrity vs. confidentiality of information from third parties.

- 50:04 Where do we start with simulating RMF?

- 52:53 Running rmf_core in the cloud or to a central location.

- 58:08 Revoking certificates. See also the [secure version of the office demo](https://github.com/osrf/rmf_demos/blob/master/docs/secure_office_world.md).

- 1:01:15 Is RMF ready for prime time? What is the short term plan for RMF?

- 1:04:10 What about "fake" robots connecting to the fleet managers?


## References

The following links were shared during the presentation:

- [RMF Demos](https://github.com/osrf/rmf_demos)
- [Office secured demo](https://github.com/osrf/rmf_demos/blob/master/docs/secure_office_world.md)
- [RMF ros2 multi robot book](https://osrf.github.io/ros2multirobotbook)
- [Free fleet](https://github.com/osrf/free_fleet), with [instructions](https://osrf.github.io/ros2multirobotbook/integration_free-fleet.html)
- [RMF Core](https://github.com/osrf/rmf_core)
- [Traffic Editor](https://github.com/osrf/rmf_core)

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
- 2020/06/09 (sid): Draft guidance for vendors on how to create a vulnerability disclosure policy.
