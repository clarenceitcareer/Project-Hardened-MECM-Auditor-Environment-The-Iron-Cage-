# Project-Hardened-MECM-Auditor-Environment-The-Iron-Cage-
Technical Overview This project demonstrates the deployment of a dual-tier Microsoft Endpoint Configuration Manager (MECM) hierarchy hosted in Azure. The primary objective was to enforce the Principle of Least Privilege (PoLP) by engineering an "Iron Cage" Group Policy environment. This allows restricted users (Auditors) to access the MECM console while being programmatically blocked from underlying Operating System tools.

Core Components

Azure Infrastructure: Domain Controller (DC01) and Site Server (CM01).

Network Security: Configured Azure Network Security Groups (NSG) to restrict RDP access to authorized Administrative IPs only.

RBAC Configuration: Assigned "Read-only Analyst" roles within MECM to segment administrative duties.

GPO Hardening: Disabled CMD.exe, the Run command, and Task Manager via User Rights Assignment and Administrative Templates.

Disaster Recovery & Troubleshooting

Resolved a global GPO lockout by utilizing the Azure Run Command and secedit to force a local security database reset.

Troubleshot WMI/SMS Provider connection errors by aligning local Remote Desktop Users groups with Domain-level permissions.
