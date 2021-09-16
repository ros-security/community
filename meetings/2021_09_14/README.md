# ROS 2 Security Working Group Meeting Minutes

14 Sep 2021

[Meeting Recording](https://youtu.be/AVZEStdIn3c) | [Meeting Announcement](https://discourse.ros.org/t/security-working-group-meeting-september-2021)

## Agenda

- [Approve WG meeting minutes for 10 Aug](#-administrivia)
- [PKCS#11 update](#pkcs11-update)
- [External CA setup](#external-ca-setup)

## Attendees

- Shaun Murphy
- Kalle Koivisto
- Ruffin White-Magner
- Marco Gutiérrez
- Jooonas Loppi
- Jacob Hassold

## Administrivia

[Minutes from the meeting on 08 Jun 2021](https://github.com/ros-security/community/pull/21) were approved.

## PKCS#11 update

Implementation going on as scheduled, e.t.a end of the year probably sooner.
We'll need to discuss SROS2 integration.

## External CA setup

Kalle is following the work on external CA setup based on Sid's doc ['HowTo: Set up a CA for ROS'](https://docs.google.com/document/d/1xvJZp9Sr3KpVZuoRGVsCsoApzrh-hj3C6gz57B68Euc/edit?usp=sharing).
Looking at how SROS2 would create domain participant key and cert requests and any external PKI service would runs the CA (thus in place of SROS2 local CA).
