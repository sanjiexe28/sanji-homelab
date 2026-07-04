# IP Addressing Plan

This document defines the IP addressing scheme used throughout the Sanji Homelab infrastructure.

---

# Network Information

| Parameter | Value |
|-----------|-------|
| Network | 192.168.0.0/24 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.0.1 |
| DNS Server | 192.168.0.1 |

---

# Infrastructure

| Hostname | IP Address | Role |
|----------|------------|------------------------------|
| RTR-01 | 192.168.0.1 | TP-Link WR802N (WISP Gateway) |
| SW-01 | 192.168.0.2 | TP-Link Omada Managed Switch |
| FW-01 | 192.168.0.3 | Netgear ProSafe VPN Firewall |
| SRV-HV01 | 192.168.0.10 | Proxmox Hypervisor |
| SRV-DC01 | 192.168.0.20 | Active Directory Domain Controller |
| SRV-DKR01 | 192.168.0.30 | Docker Host |
| SRV-MON01 | 192.168.0.40 | Monitoring Server |
| SRV-BKP01 | 192.168.0.50 | Backup Server |
| SRV-PI01 | 192.168.0.60 | Raspberry Pi Services |
| CLI-W11-01 | DHCP | Windows Workstation |
| CLI-LNX-01 | DHCP | Linux Workstation |

---

# DHCP Scope

| Parameter | Value |
|-----------|-------|
| DHCP Server | RTR-01 |
| Range | 192.168.0.100 - 192.168.0.200 |
| Lease Time | Default |

Static IP addresses below `.100` are reserved for infrastructure devices.

---

# Reserved Address Range

| Range | Usage |
|--------|-------|
| .1 - .49 | Network Infrastructure |
| .50 - .99 | Servers |
| .100 - .200 | DHCP Clients |
| .201 - .254 | Future Expansion |

---

# Future VLAN Plan

| VLAN ID | Name | Subnet | Purpose |
|---------|-------------|----------------|--------------------------|
| 10 | Management | 10.10.10.0/24 | Network Equipment |
| 20 | Servers | 10.10.20.0/24 | Virtual Machines |
| 30 | Clients | 10.10.30.0/24 | Workstations |
| 40 | IoT | 10.10.40.0/24 | IoT Devices |
| 50 | Lab | 10.10.50.0/24 | Testing Environment |
| 99 | Native | 10.10.99.0/24 | Native VLAN |

---

# Notes

- Infrastructure devices use static IP addresses.
- Client devices receive IP addresses via DHCP.
- Future VLAN segmentation will be implemented after deploying the firewall and Proxmox environment.