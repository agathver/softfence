# SoftFence

A tool for generating linux security policies.

## Background

Writing linux security policies are hard. Think about the complexity of SELinux and AppArmour. Both of these are insanely powerful but notoriously difficult to configure.

The initial idea stemmed from the talk I presented at Flock 2018 (Fedora Contributors Conference) -- goal of which was to make software more secure by making it easier to include sandboxing and confining configuration.

A major blocker for open-source packages is that the universe of Linux Security Modules (LSMs) is fragmented, RHEL, Fedora and CentOS use SELinux an Ubuntu uses AppArmour. It is inconvenient to actually maintain configuration sync between two implementations.

## Design

SoftFence uses a DSL to specify simple confinement and firewall rules. It then uses one of the specific backends to generate and apply LSM specific configuration.

## Other potential use-cases

* Hardening container infrastructure by generating AppArmor or SELinux rules.