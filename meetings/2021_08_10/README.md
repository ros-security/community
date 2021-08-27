# ROS 2 Security Working Group Meeting Minutes

10 Aug 2021

[Meeting Recording](https://youtu.be/YwpZgNoYsd8) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-august-2021)

## Agenda

- [Approve WG meeting minutes for 08 Jun](#-administrivia)
- [Shaun introduction](#shaun-introduction)
- [PKCS#11 Design update](#pkcs1111-design-update)

## Attendees

- Marco Gutiérrez
- Gianluca Caiazza
- Cameron Mott
- Kalle Koivisto
- Jacob Hassold
- Shaun Murphy
- Jeremie Deray

## Administrivia

[Minutes from the meeting on 08 Jun 2021](https://github.com/ros-security/community/pull/21) were approved.

## Shaun introduction

Shaun introduced himself and explained the chair change.
After what he re-assured of Canonical commitment to the WG;
Canonical is back filling the position.

## PKCS#11 Design update

Summer time, people are either coming back from vacation or just starting them.
Kalle said that Eprosima started the implementation for the integration of PKSC#11 in Fast-DDS with a planned timeline set for the end of the year.
He also did a brief recall on the design: PKCS URI fed to openSSL in Fast-DDS;
on SROS2 side, the key name will be given in the configuration file.
The reference implementation is going to be done against softHSM.
Normally, 'real' HSM solution should be fairly easy to integrate since PKCS11 makes the back-end replaceable.
