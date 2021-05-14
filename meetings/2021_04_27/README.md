# ROS 2 Security Working Group Meeting Minutes
27 April 2021


## Agenda

- Approve WG meeting minutes for 13 APR
- Using a `data:` or `pkcs11:` URI with DDS security


## Attendees

Gianluca Caiazza,
[Jeremie Deray](https://github.com/artivis),
Kalle Koivisto,
[Phil Wolff](https://github.com/evanwolf),
[Roger Strain](https://github.com/roger-strain),
[Sid Faber](https://github.com/sidfaber)
Tomoya Fujita


## Drone use case

Discussed by Kalle: Consider the scenario where a swarm of drones uses ROS 2 to communicate within the drone and between drones.
The swarm also has a ground control that is the trust anchor for comms within the swarm.
The idea is still under design, but the issue is to have a central key store within the enclave.
They're hoping to implement DDS to support the central key store and consume keys over PKCS 11.

They're currently using FastRTPS which does not appear to support PCKS 11, but they're willing to contribute to FastRTPS and potentially to SROS to build the implementation.
The FastRTPS middleware is most commonly used by the drone community.

This may also open the need to revisit the idea of securing ROS on a constrained environment without a file system.

References (links shared during the meeting):
 - An example [WIP document](https://docs.google.com/document/d/1xvJZp9Sr3KpVZuoRGVsCsoApzrh-hj3C6gz57B68Euc/edit#heading=h.85wyx39e3qj5) on using an external certificate store; this document will eventually be proposed into the [ROS 2 tutorials](https://docs.ros.org/en/foxy/Tutorials.html).
 - The [rcl issue](https://discourse.ros.org/t/ros-2-without-a-file-system/16942/2) that led to the [discourse discussion](https://github.com/ros2/rcl/issues/545) on running ROS without a file system

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
