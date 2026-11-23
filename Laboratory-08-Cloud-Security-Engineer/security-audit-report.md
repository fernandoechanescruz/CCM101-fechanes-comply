# Security Audit Report

## The Principle of Least Privilege (PoLP)
The Principle of Least Privilege means granting a user, program, or process only the permissions it needs to do its job, and nothing beyond that. It matters for cloud user accounts because if an over-privileged account is ever compromised, an attacker can do as much damage as that account was permitted to reach. A tightly scoped account keeps one breach from turning into a full system compromise.

## Attack Surface
The attack surface of a virtual machine is the total number of points through which an unauthorized person could potentially get in. Every open port, running service, installed package, and user account adds to it. The smaller the attack surface, the fewer chances an attacker has to find a weakness, which is why hardening a server means disabling or removing everything that is not strictly needed.

## Default Deny Policy
Blocking all traffic by default and allowing only specific, known-necessary connections is safer than trying to block known attackers one by one, because it is impossible to predict every malicious IP address or attack pattern ahead of time. A default deny policy treats all traffic as untrusted until it is explicitly shown to be safe. This shuts out every unknown or future threat instead of reacting to each one after it has already happened.
