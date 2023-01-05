# ROS 2 Security Working Group Meeting Minutes
13 December 2022
[Meeting Recording](https://www.youtube.com/watch?v=NOwY3R3Nx10) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-december-2022/28373)
 
## Agenda
- (Florencia) Approval requested: [Add minutes from meeting on November 08, 2022](https://github.com/ros-security/community/pull/43)
 
## Attendees
 
- Gianmarco Pisanelli (AMRC)
- Benjamin Morrow (AMRC)
- Ruffin White
- Eduardo Ponz (eProsima)
- Florencia Cabral (Canonical)
- Patrick Dahlke (Apex.AI)
- Yen Yuthnea
 
## Administivia
 
### Approve last meeting minutes
 
[Minutes from the meeting on November 08, 2022](https://github.com/ros-security/community/pull/43) were approved.
 
## Discussion
 
* The group hosted Gianmarco Pisanelli and Ben Morrow from the [Advanced Manufacturing Research Centre (AMRC)](https://www.amrc.co.uk/) at the University of Sheffield, who gave a presentation about vulnerabilities they discovered in DDS.
* Description of the issue: Currently the security keystores created by ros2 security use a single CA symlinked as both Identity CA and Permissions CA. This opens a security hole where a malicious node can sign its own permissions document with the following steps:
 * The node creates a new permissions.xml and signs it with its own enclave certificate and private key.
 * The node publishes the signed document over DDS as usual.
 * Other nodes attempt to verify the signature; since the enclave certificate is signed by the Identity CA, and the Identity CA is the same as the Permissions CA, the signature is accepted.
* Because there is a chain of trust between this joint CA through the nodes' own certificates, to the new document, other nodes will believe it is authentic.
* It does not seem possible to work around this issue by removing certificate flags; the enclave certificate must have the `digitalSignature` flag to be able to prove its identity and participate in Secure DDS. The solution is to separate the two CA roles into different certificates. That way, although the node could sign a document with its enclave certificate, that document would no longer be trusted because the enclave certificate would not be signed by the Permissions Authority. This would restore the ability to set proper ACLs on the nodes.
* Ben shared a shell script that demonstrates the problem (available as part of [this Github issue](https://github.com/ros2/sros2/issues/282)), and shared a demo during the meeting.
* Eduardo Ponz (eProsima) shared the open [design proposal to support PKCS#11 URIs](https://github.com/ros2/design/pull/319), as an alternative to private keys and certificates stored in the file system.
* Another issue that was brought up relates to key management. When `create_enclave` is run, it generates a key and signs the certificate in a single step. This gives the option to either run this step on the machine where it will be used, or the one that has access to the CA key. The advised approach currently is to run in a separate machine isolated from the robot, then deploy on the robot. However, this is not the best in terms of security practices, as SROS2 does not seem to have an effective mechanism for key transmission between remote nodes.
* The following action points were agreed upon:
 * Improve security examples in ROS 2 docs (Eduardo Ponz)
 * Revive the design proposal to support PKCS#11 URIs (Eduardo Ponz)
 * Look into splitting the CAs, and verifying the chain of trust (Ruffin White)
 * Create issues in the sros2 repo to reflect the findings (Ben Morrow)
   * Issue open: [Chain of trust issues with a single CA certificate](https://github.com/ros2/sros2/issues/282)
   * Issue open: [SROS2 does not seem to have an effective mechanism for keys transmission between remote nodes](https://github.com/ros2/sros2/issues/283)
 
 

