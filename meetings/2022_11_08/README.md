# ROS 2 Security Working Group Meeting Minutes
 
08 November 2022
[Meeting Recording](https://youtu.be/MDPYzRIm-ho) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-november-2022/28049)

## Agenda
 
- (Florencia) Approval requested: [Add minutes for meeting on September 13, 2022](https://github.com/ros-security/community/pull/42)

## Attendees

- Michael Jeronimo, Open Robotics
- Adam Mitz, Object Computing Inc.
- David Anthony, Southwest Research Institute
- Meera Towler, Southwest Research Institute
- Jeremie Deray (artivis), Canonical
- Florencia Cabral Berenfus, Canonical

## Administivia

### Approve last meeting minutes

[Minutes from the meeting on September 13, 2022](https://github.com/ros-security/community/pull/42) were approved.

## Discussion

- We had a guest presentation by Michael Jeronimo from Open Robotics, who is working on the [Space ROS project](https://github.com/space-ros/space-ros). Some of the main points touched on: 
    - an overview of 3 aspects of Space ROS: Foundation, Tools and processes, and Space-specific functionality,
    - the ongoing process for space certification, including tools being used for requirements management,
    - code quality analysis tools being used such as [IKOS](https://github.com/space-ros/ikos) and [Cobra](https://github.com/nimble-code/Cobra) with SARIF format input; an integration and analysis dashabord for issue navigation, visualization and dispositioning; and adding dynamic analysis such as MC/DC testing.
    - Contributions and input to the Space ROS project are welcome. Some possible areas include contributing to the VS Code SARIF Viewer, SARIF filtering, or the VS Code-based Docker workflow.
- A discussion followed that touched, among other issues, on their efforts to integrate open source tools and processes to help improve software quality in the community. There is space for defining a quality level for ROS packages in terms of security.