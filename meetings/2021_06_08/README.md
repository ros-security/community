# ROS 2 Security Working Group Meeting Minutes
08 Jun 2021

[Meeting Recording](https://youtu.be/YwpZgNoYsd8) | [Meeting Announcement](https://discourse.ros.org/t/security-wg-meeting-june-8-2021/20806)


## Agenda

- Approve WG meeting minutes for 11 May
- PKCS#11 design proposal for FastDDS and SROS2
- ROS 2 `sros2` documentation update PR


## Attendees

Bartolome	Jimenez Vera,
Iker	Luengo Gil,
Jacob Hassold,
Jeremie	Deray,
Kalle	Koivisto,
Marco	Gutiérrez,
Mikael	Arguedas,
Roger	Strain,
Ruffin White,	
Sid	Faber,
Tianshi	Xiang


## Administrivia

[Minutes from the meeting on 11 May 2021](https://github.com/ros-security/community/pull/20/files) were approved.

## PKCS#11 Design Proposal

Iker and Kalle presented a simple proposal for adding `pkcs#11` support to ROS 2.
The intent is to make sros aware of a `.p11` file type with the same name as the security key.
ROS would recognize this file exists and read the file as a PKCS URI and hand the URI off to the middleware.
ROS will not pass the .p11 file to the middleware (that would not be compliant with the DDS standard), but would deserialize the .p11 file and treat it as a PKCS URI.

Current plans skip any changes to the encryption plugin and only address the authentication plugin.
The primary intent is to protect the private keys.

Should an implementation have both a .p11 and a .key file (or a similar related unexpected situation), generate an error rather than trying to implement some priority logic.

This change may include updates to sros2 utilities to easily enroll with PKCS and generate the needed artifacts.

DDS vendors should be made aware of the change, although it should have minimal impact.


## Documentation Update PR

Sid gave an overview of the [ROS 2 Security documentation update PR](https://github.com/ros2/ros2_documentation/pull/1662).
Please review / comment.


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

