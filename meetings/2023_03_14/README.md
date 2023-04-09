# ROS 2 Security Working Group Meeting Minutes
14 March 2023
[Meeting Recording](https://youtu.be/sd8CGz5-Vpg) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-march-2023/30184)
 
## Agenda
- (Florencia) Approval requested: [Add minutes from meeting on February 14, 2023](https://github.com/ros-security/community/pull/47)
 
## Attendees
 
- Kalle Koivisto (Unikie / TII SSRC)
- Patrick Dahlke (Apex.AI)
- Florencia Cabral (Canonical)
- Ruffin White
- Gianluca Caiazza
 
## Administivia
 
### Approve last meeting minutes
 
[Minutes from the meeting on February 14, 2023](https://github.com/ros-security/community/pull/47) were approved.
 
## Discussion
 
- Florencia shared 2 ament wrappers recently developed to integrate static analysis tools: Bandit (supporting Python code) and Semgrep (security rule engine supporting Python, C++, XML, JSON, among others). The Github repos can be found here: [ament_bandit](https://github.com/florcabral/ament_bandit), [ament_semgrep](https://github.com/florcabral/ament_semgrep). Some questions and feedback referred to the output formats (Xunit is preferred), ROS-specific implementation aspects, interest from the WG to support the project, and target repository for upstream contribution. Other members will test the wrappers, and they would be proposed to the [ament_lint](https://github.com/ament/ament_lint) repo.
- Discussion on whether SROS is being used with other middlewares aside from DDS. It has been discussed to get a Zenoh RMW layer, with [zenoh](https://zenoh.io/) support for security features using TLS. This could be helpful for generalizing the security artifact material for deployment, as currently there is only an example for using secure DDS.
- Update on PKCS#11 PR: The most recent feedback requests to not propose the project via the design repo, which is being deprecated, and open a formal REP instead.
