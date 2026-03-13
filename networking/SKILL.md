---
name: networking
version: 0.0.1
description: |
  Guidance for TalTech networking work. Focus on protocols, connectivity,
  addressing, troubleshooting, security basics, and practical network-aware
  application design.
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash
---

# TalTech Networking

## Focus areas

- OSI and TCP/IP reasoning
- addressing and subnetting basics
- service connectivity
- request/response troubleshooting
- network assumptions inside apps

## Expectations

- explain which layers are relevant to the problem
- identify hosts, ports, protocols, and paths explicitly
- separate DNS, routing, firewall, and application-level issues clearly

## Review checklist

Review for:

- confused protocol explanations
- hidden network assumptions
- poor handling of timeouts or connectivity errors
- security blind spots in exposed services

Prefer explicit explanations of how components talk to each other.

## Expected output

Good guidance should identify:

- source and destination
- protocol and port
- what layer the problem lives at
- how to verify the hypothesis
