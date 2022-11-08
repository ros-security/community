# ROS 2 Security Working Group Meeting Minutes
 
13 September 2022
[Meeting Recording](https://youtu.be/4WZHi23MV0E) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-september-2022/27260)

## Agenda
 
- (Florencia) Approval requested: [Add minutes for meeting on July 12, 2022](https://github.com/ros-security/community/pull/41)
 
## Attendees

- Kalle Koivisto
- Roger Strain
- Florencia Cabral

## Administivia

### Approve last meeting minutes

[Minutes from the meeting on July 12, 2022](https://github.com/ros-security/community/pull/41) were approved.

## Discussion

- There has been work over the last few months to enhance FastDDS, to add support for multilayer networks to communicate seamlessly, where ROS security features are enabled too.
- Further discussion around rewriting ROS 2 nodes to move to memory safe languages (ie, Rust). Attendees exchanged information about other projects/developers already doing this, ie [this Github page](https://github.com/jhdcs).
- Discussion around [Zenoh](https://zenoh.io/), following its presentation to [the last TSC meeting](https://discourse.ros.org/t/ros-2-tsc-meeting-minutes-8-18-2022/27050), and the security implications of this. For example, how can there be SROS2 support for Zenoh?
