# ROS 2 Security Working Group Meeting Minutes
23 Feb 2021

[Meeting Recording](https://youtu.be/WxEUQD7NnSA) | [Meeting Announcement](https://discourse.ros.org/t/ros-2-security-working-group-meeting-23-feb-2021/19094)


## Agenda

- Approve WG meeting minutes for 09 FEB
- (Marco) Update on RMF use case
- (Sid, 5min) Update on MoveIt use case


## Attendees

[Jacob Hassold](https://github.com/jhdcs),
[Jeremie Deray](https://github.com/artivis),
Kalle Koivisto,
[Marco Gutierrez](https://github.com/marcoag),
[Roger Strain](https://github.com/roger-strain),
[Sid Faber](https://github.com/sidfaber)


## Administrivia

[Minutes from the meeting on 09 FEB 2021](https://github.com/ros-security/community/pull/15/files) were approved.

Monitor [SROS2 ISSUE 252: Default RMW no longer ships with DDS security features](https://github.com/ros2/sros2/issues/252).

## Use Cases
Marco provided an update on RMF security with a [list of RMF security needs](https://docs.google.com/document/d/1cGl00uS2OQ9Eg5c-G-U2gwBsfKYaVZHKuSZrf4uoBeE/edit). There's some overlap between Marco's work with Jeremey's logging work and Ted's work on NoDL:

- Certificate revocation is the #1 use case, need something like a `revoke_permissions` API.

- Need to be able to use the CLI tools when security is enabled. Jeremey remarked that this can potentially be covered through NoDL.

- Interested in implementing CA hierarchies to see if they help with revocation

- Looking for security to suppor some assertion of third party security, vendor guidelines, etc.

- Require some form of setup testing. After the security environment is set up, check that the setup is correct and everything is working. Some of this may be met through the logging plugin (in progress)

- Secure launch; generate detailed policies from a NoDL description.

Sid provided an update on the MoveIt use case. A LXD container is provided by MoveIt with a working demo that can be used to implement security. A test case will be to create a read-only extension of the LXD container that can be used to monitor the robot state.


## Documentation question

Kalle opened a discussion on implementing security for a fleet of drones:

- What are the diffeent encryption/authentication schemas?

- What controls do we have to change them?

- Can SROS fetch the keys?

- What documentation exists?

A discussion ensued, with a reference to the [DDS spec](https://www.omg.org/spec/DDS-SECURITY/1.1/PDF) and the current state of SROS implementation and documentation.


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
