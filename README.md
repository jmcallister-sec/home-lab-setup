🏠 Home Lab — Security Operations & Detection Engineering
A living documentation of my personal security home lab, built to support Blue Team skill development, network analysis, and threat detection practice. Updated as the lab evolves.


📋 Overview
This lab is designed to simulate a small enterprise environment for hands-on practice with security monitoring, network traffic analysis, identity and access management, and incident response fundamentals.

Primary Goals:

Support Security+, BTL1, and AZ-500 certification study with practical application
Build foundational skills in network traffic analysis, log review, and detection
Create a realistic environment for Wireshark captures and AD attack/defense scenarios
Document build decisions, issues encountered, and lessons learned


🗺️ Architecture
Network Design
ISP

 └── UCG-Fiber (UniFi Gateway)

      └── USW-Lite-8-PoE (Switch)

           ├── VLAN 10 — Trusted (daily use devices)

           ├── VLAN 20 — Lab (pfSense VM, Windows Server, Linux)

           ├── VLAN 30 — IoT (cameras, smart home)

           └── VLAN 99 — Management
Lab VLAN Components (VLAN 20)
Host
OS
Role
lab-fw-01
pfSense
Firewall / traffic inspection
lab-dc-01
Windows Server 2022
Active Directory Domain Controller
lab-ws-01
Windows 10
Domain-joined workstation
lab-kali-01
Kali Linux
Attack simulation / tooling
lab-ubuntu-01
Ubuntu 22.04 LTS
General Linux / log analysis

Physical Hardware
Component
Details
Gateway
UniFi UCG-Fiber
Switch
USW-Lite-8-PoE
Access Points
2x U7 Pro
NAS
Synology DS224+ (RAID 1)
Virtualization
[To be added — hypervisor TBD]



🔧 Build Log
Phase 1 — Physical Network (In Progress)
Install UCG-Fiber gateway
Configure USW-Lite-8-PoE with VLANs
Run Cat6a drops (4 locations)
Mount and configure U7 Pro APs
Validate inter-VLAN routing and firewall rules
Phase 2 — Lab VLAN Standup
Deploy pfSense VM on Lab VLAN
Deploy Windows Server 2022 — Active Directory
Join Windows 10 workstation to domain
Deploy Ubuntu 22.04 LTS host
Configure Wireshark capture on Lab VLAN
Phase 3 — Detection & Monitoring
Configure Sysmon on Windows hosts
Centralize logs (syslog / Windows Event Forwarding)
Run first Wireshark capture sessions
Begin PCAP analysis lab exercises


🧠 Design Decisions & Rationale
Why pfSense?
pfSense provides enterprise-grade firewall features in an open-source package. Using it in the lab builds familiarity with stateful packet inspection, firewall rule construction, and traffic logging — all directly applicable to SOC and threat detection work.
Why UniFi for the physical network?
UniFi's controller-based management mirrors how enterprise network infrastructure is managed at scale. Working with the UniFi dashboard builds intuition for segmentation, VLAN policy enforcement, and network visibility that translates directly to security operations contexts.
Why Active Directory?
The majority of enterprise environments run Microsoft AD. Understanding its structure — users, groups, OUs, GPOs, Kerberos authentication — is foundational for both threat detection (e.g., recognizing abnormal authentication patterns) and understanding attack paths documented in MITRE ATT&CK.
Why a separate Lab VLAN?
Isolating lab traffic prevents experimental or potentially noisy activity from affecting production home network devices, and creates a clean capture boundary for Wireshark analysis.


🚧 Issues & Resolutions
This section tracks problems encountered during the build and how they were resolved. Updated as the lab progresses.

Date
Issue
Resolution
Lesson
—
—
—
—



📚 Resources Referenced
Practical Networking — Ed Harmoush
Professor Messer — CompTIA Security+
Jeremy's IT Lab — CCNA (YouTube)
MITRE ATT&CK Framework
Malware Traffic Analysis (PCAP resources)


🗓️ Roadmap
Phase
Target
Status
Physical network build
Q2 2026
🔄 In Progress
Lab VLAN & AD standup
Q3 2026
⏳ Planned
First Wireshark captures
Q3 2026
⏳ Planned
BTL1 lab exercises
Q1 2027
⏳ Planned
Azure cloud lab (AZ-500 prep)
Q2 2027
⏳ Planned
