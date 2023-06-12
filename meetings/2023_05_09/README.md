# ROS 2 Security Working Group Meeting Minutes
09 May 2023
[Meeting Recording](https://www.youtube.com/watch?v=Xis_r6CLnyw&feature=youtu.be) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-may-2023/31232)
 
## Agenda
- (Florencia) Approval requested: [Add minutes from meeting on April 11, 2023](https://github.com/ros-security/community/pull/49)
 
## Attendees
 
- Kalle Koivisto (Unikie, TII SSRC)
- Florencia Cabral (Canonical)
- Marco Gutierrez
 
## Administivia
 
### Approve last meeting minutes
 
[Minutes from the meeting on April 11, 2023](https://github.com/ros-security/community/pull/49) were approved.
 
## Discussion
 
- Florencia requested feedback from the group on ament wrappers: [ament_bandit](https://github.com/florcabral/ament_bandit/tree/main) and [ament_semgrep](https://github.com/florcabral/ament_semgrep)
- Marco shared [a library versioning issue](https://github.com/ros2/sros2/issues/285) affecting the SROS package. This issue is caused by an attribute that has been removed from PKCS#7. It affects Windows currently, but will affect Linux in the future when OpenSSL is updated.
