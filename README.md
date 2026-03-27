
# Linux Privilege Escalation – Insecure Sudo Configuration

## Overview

This lab demonstrates how improper sudo configurations can lead to privilege escalation on a Linux system.

Sudo allows non-root users to execute commands with elevated privileges. However, misconfigurations can allow unintended access to root-level functionality.

This project explores how insecure sudo rules can be abused to gain a root shell.

---

## Key Concepts

- Sudo misconfiguration
- Principle of Least Privilege
- Privilege escalation
- Linux security hardening

---

## Vulnerability

The sudo configuration allows a user to execute certain binaries without requiring a password.

Example from `/etc/sudoers`:
admin ALL=(ALL) NOPASSWD: /usr/bin/less, /usr/bin/base64, /usr/bin/file


This violates least privilege and introduces risk.

---

## Exploitation Method

The `less` command can be abused to execute shell commands.

Steps:

1. Run: sudo less /etc/passwd

2. Inside `less`, execute: !/bin/sh


3. Gain root shell access

---

## Impact

- Full root access obtained
- System compromise
- Bypass of authentication controls

---

## Mitigation

- Remove NOPASSWD where not required
- Restrict allowed binaries
- Enforce least privilege
- Regularly audit `/etc/sudoers`

---

## Proof of Concept

See attached document:

[Privilege Escalation Insecured Sudo](./PrivEsc-Insecure-Sudo.pdf)

---

## Skills Demonstrated

- Linux Security
- Privilege Escalation
- Sudo Configuration Analysis
- Threat Identification
- Security Hardening

