# ROS 2 Security Working Group Meeting Minutes
10 May 2021

[Meeting Recording](https://youtu.be/bxJ-EJ_6LxM) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-may-2021/20270)


## Agenda

- Approve WG meeting minutes for 13 APR and 27 APR
- (Kalle) Using a data: or pkcs11: URI with DDS security


## Attendees

Gianluca Caiazza,
Jeremie Deray,
Sid Faber,
Tomoya Fujita,
Marco Gutiérrez,
Jacob Hassold,
Kalle Koivisto,
Iker Luengo Gil,
Víctor Mayoral Vilches,
Manuel Segarra-Abad,
Roger Strain,
Ruffin White-Magner,
Tianshi Xiang


## Administrivia

[Minutes from the meeting on 13 APR 2021](https://github.com/ros-security/community/pull/18) were approved.

[Minutes from the meeting on 27 APR 2021](https://github.com/ros-security/community/pull/19) were approved.


## `pkcs11:` URI Support

Kalle Koivisto
[presentated slides (pdf](2021-05-ROS2SecurityWGpresentation.pdf), [pptx)](2021-05-ROS2SecurityWGpresentation.pptx)
on his project to create a platform for drone fleets.

The platform allows a drone fleet to perform missions autonomously.
It contains cloud, fog and edge compute drones.
All parts of the fleet run in a ros network, both between drones and within drones.
Zones within the drone are logically divided with a hypervisor and virtual machines.

A crypto back end on the drone should be used to safely store keys and provide crypto access via PKCS#11.
The current struggle is finding best way to protect the ROS private keys, preferably with PKCS11 API.
Although the DDS spec supports PKCS, the middleware does not seem to have implemented this.
PKCS may also be used for other (non-ROS) crypto options, but all the private keys must be stored in a hardened isolated crypto back end.

The implementation is similar to a typical/standard provisioning implementation for encryption trust.
The drone generates its own key pair and a Certificate Signing Request (CSR) that is signed by the cloud.
The local file system can still store the identity cert, permissions file and CAs.
PKCS would be used to access secrets stored in the secure back end, not on the file system: sign, encrypt, decrypt with pkcs11.
This allows the crypto back end to be fully replaceable, enables many different use cases.

### Q&A

Iker: The preso is quite clear.
FastDDS does not yet support pkcs.
It's unclear how much work is required to support pkcs, but it's worth exploring.
Open to starting to work on this.

Ruffin: Would the certificates be in-band our out-of-band?
Probably out-of-band during a provisioning phase.
The sros2 api would need updated to support creating/issuing the certs, etc.

There's an open issue on the state of PKCS11 in python's crypto library.
The current implementation had to help with their s/mime signing support.

This will require a ROS 2 design change to specify how to configure PKCS URIs.

There is currently no need to support `data:` URIs.
For this use case each drone has a local file system for storing security files.

Certificate revocation lists (CRLs) are currently not supported.
CRLs are a nice-to-have so drones can be removed from the fleet.


### Next steps

Iker and Calle to work on the way forward.
This likely will start with an updated design doc to support PKCS URIs.



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
