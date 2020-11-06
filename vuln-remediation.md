# Vulnerability Remediation

This document describes the typical process for remediating security vulnerabilies in ROS 2, including those submitted through the process  described in [REP 2006, ROS 2 Vulnerability Disclosure Policy](https://www.ros.org/reps/rep-2006.html).

## Roles

The vulnerability remediation process relies upon the following roles:

### Reporter

The individual or organization reporting a vulnerability within ROS. The Reporter may have no prior knowledge of ROS including versioning, repositories or project governance.

### Coordinator

The individual responsible for facilitating the coordinated response process. This includes triaging the initial vulnerability report, identifying a Maintainer responsible for fixing the vulnerability, and tracking the report to a resolution. The Coordinator must, to the best of his or her ability, protect the confidentiality of the vulnerability until a fix has been published.

### Maintainer

The individual or organization responsible for updating the code base to eliminate the vulnerability. The Maintainer also must, to the best of his or her ability, protect the confidentiality of the vulnerability until a fix has been published.

These roles generally align with standard definitions in [The CERT Guide to Coordinated Vulnerability Disclosure](https://vuls.cert.org/confluence/display/CVD/3.+Roles+in+CVD); however, our *Maintainer* assumes the duties of *Deployer*, and the *Coordinator* also assumes the duties of the *Vendor* and works with Open Robotics as needed.

## Process

This process begins with a vulnerability report sent to [security@openrobotics.org](mailto:security@openrobotics.org).

1. **Assign a Coordinator.** Members of the `security` distribution list must reach consensus on the individual to take ownership of the issue. OpenRobotics will assign a Coordinator when consensus cannot be reached.

1. **Triage.** The Coordinator must quickly determine the severity of the vulnerability.  The Coordinator should perform some or all of these tasks to accurately triage the vulnerability and begin handling the vulnerablity:

   1. **Coordinator acknowledges the report and seeks additional details.** This may require setting up a secure communications channel between the Reporter and the Coordinator. Not all vulnerability reports will need to establish secure comms, but the option should always be available. See below for information to consider requesting from the Reporter.

   1. **Coordinator confirms scope and applicability.**  If the vulnerability is not in scope or not applicable the Coordinator provides feedback to the Reporter. In addition to noting that the vulnerability was not accepted, feedback may include additional guidance such as [how to contact the ROS 2 Security Working Group](https://github.com/ros-security/community#communication-channels).

   1. **Coordinator assigns a severity.** Severity generally should follow the [Common Vulnerability Scoring System (CVSS)](https://www.first.org/cvss/calculator/3.0), although the CVSS results may be adjusted to account for unique concerns.

   1. **Coordinator identifies and notifies the responsible Maintainer.** When a vulnerability is in scope, follow "additional guidance" below on how to identify the Maintainer. If secure communications have been established with the Reporter, secure communications should also be set up with the Maintainer. Use the following template to reach out to the Maintainer, include a copy of the message to [security@openrobotics.org](mailto:security@openrobotics.org) (the template may be modified as needed to fit the situation):

      > SUBJECT: [HIGH | Medium | Low] risk security vulnerability in [package name]
      > 
      > A [HIGH | Medium | Low] risk security vulnerability has been identified in [package name].  Please contact me at [contact] to discuss the vulnerability details.
      > 
      > [include if needed] Based on the severity of the vulnerability, the details are particularly sensitive and need to be protected through secure communications. Please send me your public PGP key through which you can receive secure email; if you are unable to send and receive secure email, please let me know and we will establish another secure channel.
      > 
      > [Attach a PGP key or a Key ID]
      >
      > [Sign the email with the PGP key]
      >

   1. **Coordinator registers a CVE.** Seek help from the [ROS 2 security working group](https://github.com/ros-security/community#communication-channels) if necessary to reserve the CVE. The reserved CVE should not include any detailed information; this will be added after disclosure. All subsequent communications should include the CVE numnber for traceability.

1. **Remediation**

   1. **Maintainer fixes the vulnerability.** Work should be done locally as much as possible; when the fix is pushed to github the fix becomes visible to the public even though the patch has not been released to users. The final pull request for the fix should include a reference to the CVE in comments for traceability.

   1. **Coordinator tracks to completion.**  This likely will mean periodic update requests to the Maintainer until the Maintainer publishes a fix. Seek assistance from the Security WG if needed.

   1. **Coordinator plans for vulnerability disclosure.** For high risk vulnerabilities or fixes with significant impact, create a communications plan for patch release and full disclosure. The plan should take input from the Maintainer and the Reporter.

1. **Disclosure**

   1. **Maintainer conducts patch pre-notification.** When the fix is ready for release, the Maintainer, at his or her discretion, will notify select individuals that the fix is ready. This notification should be specifically to quickly remediate any build issues caused by the patch, to merge the pull request, monitor as the patch is bloomed, and finally confirm the fix is sync'd into the ROS distro.

   1. **Coordinator notifies the Reporter that the patch has been released.** At this point the patch is available as an update to ROS users.

   1. **Disclose the patch to a broader audience as desired.** Follow the vulnerabilty disclosure plan if one exists. Consider notifying the ROS community of the patch availability; for example, with a general post to [ROS discourse](https://discourse.ros.org/).

   1. **Coordinator updates CVE details.** Include a link to the patch and final CVSS details. 


## Additional Guidance

### Identifying the Maintainer

If the Maintainer of the vulnerable package is not well known, review recent activity for the package. Contact pull request approver(s) to find a responsible person.

### Requesting information from the Reporter

Reporters may have a wealth of additional details about the vulnerability which they are willing to share when asked.  Consider requesting some or all of the following:

 - Operating system
 - ROS distro
 - ROS package
 - Robot that you were testing
 - How to reproduce the issue
 - Do you have / can you provide a git patch to fix the issue?
 - Do you have a docker image, a snap, or similar artifacts to share?

### Unresponsive Maintainers

As documented in [REP 2004, Package Quality Categories](https://ros.org/reps/rep-2004.html), ROS packages at quality level 1 and 2 are required to follow disclosure guidelines. The Coordinator should remind the Maintainer of their obligations under REP 2004, and escalate to the ROS 2 [Technical Steering Committee](https://index.ros.org/doc/ros2/Governance/) if necessary.


### The `security@openrobotics.org` distribution list

This email distribution list is to be used exclusively for the public to report ROS vulnerabilities. Unless explicitly labeled otherwise, conversations to the list are considered private and confidential. Follow the [CISA Traffic Light Protocol (TLP)](https://www.cisa.gov/tlp) guidance for TLP:RED information usage and sharing.

Distribution list membership will be maintained by Open Robotics. Membership must be broad enough to ensure coverage for timely response to Reporters. No email aliases or shared mailboxes may be included in the list.

Individuals added to the distribution list must adhere to the following principles:
 - You must be able to take ownership of reported vulnerabilities and act as the Coordinator through remediation. When high risk vulnerabilities are reported, this means vulnerability coordination becomes your highest priority until a fix is released.
 - You must reach out to the Security Working Group or individual members of the Working group when you need assistance in handling vulnerability reports.
 - You must be able and willing to handle PGP-encrypted email.


