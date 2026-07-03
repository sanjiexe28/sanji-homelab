# Naming Convention

This document defines the naming standards used throughout the Sanji Homelab project.

---

## Infrastructure Prefixes

| Prefix | Description | Example |
|----------|------------------------|------------|
| RTR | Router | RTR-01 |
| FW | Firewall | FW-01 |
| SW | Switch | SW-01 |
| SRV | Server | SRV-DC01 |
| CLI | Client Workstation | CLI-W11-01 |
| AP | Access Point | AP-01 |
| NAS | Network Attached Storage | NAS-01 |

---

## Server Roles

| Name | Description |
|---------|-------------------------|
| SRV-HV01 | Proxmox Hypervisor |
| SRV-DC01 | Active Directory |
| SRV-DKR01 | Docker Host |
| SRV-MON01 | Monitoring |
| SRV-BKP01 | Backup Server |
| SRV-PI01 | Raspberry Pi Services |

---

## Documentation IDs

| Prefix | Description |
|----------|----------------|
| SHL-NET | Networking |
| SHL-PVE | Proxmox |
| SHL-AD | Active Directory |
| SHL-LNX | Linux |
| SHL-DKR | Docker |
| SHL-SEC | Security |
| SHL-MON | Monitoring |
| SHL-BKP | Backup |

---

## Commit Convention

```
feat:
fix:
docs:
refactor:
chore:
```