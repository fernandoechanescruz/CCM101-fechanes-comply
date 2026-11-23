# Laboratory Activity 8: Mission 8 – The Cloud Security Engineer

## Mission Overview
This lab puts defense-in-depth into practice by securing a live server with a host-based firewall. I deployed an exposed web application, audited its open ports, and set up UFW with a Default Deny policy that blocks every connection except the specific services the application needs.

## Objectives
- Understand what the Attack Surface is and how the Principle of Least Privilege applies
- Carry out a basic security audit of active network ports
- Set up UFW with a Default Deny policy
- Apply granular port management for SSH and HTTP traffic

## Commands Executed
- `docker run -d --name secure-web-app -p 8080:80 nginx` — deployed the exposed web app
- `sudo ufw allow ssh` — allowed SSH before enabling the firewall
- `sudo ufw default deny incoming` / `sudo ufw default allow outgoing` — set the Default Deny policy
- `sudo ufw enable` — activated the firewall
- `sudo ufw status verbose` — confirmed the active rules
- `sudo ufw allow 8080/tcp` — opened the port the web app needs
- `sudo ufw status numbered` — verified the new rule

## Skills Learned
- Setting up a host-based firewall with a Default Deny policy
- Recognizing why the order of rules matters, with SSH allowed before the firewall is enabled
- Managing individual ports precisely to keep a server's attack surface small
- Writing clear security documentation for other engineers
