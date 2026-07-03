# IP Addressing Plan

## Network

```
192.168.1.0/24
```

Gateway

```
192.168.1.1
```

DNS

```
192.168.1.1
```

---

## Infrastructure

| Hostname | IP Address | Description |
|------------|--------------|----------------|
| RTR-01 | DHCP | TP-Link WR802N |
| SW-01 | 192.168.1.2 | TP-Link Omada Switch |
| FW-01 | 192.168.1.3 | Netgear Firewall |
| SRV-HV01 | 192.168.1.10 | Proxmox Hypervisor |
| SRV-DC01 | 192.168.1.20 | Domain Controller |
| SRV-DKR01 | 192.168.1.30 | Docker Host |
| SRV-MON01 | 192.168.1.40 | Monitoring |
| SRV-BKP01 | 192.168.1.50 | Backup Server |
| SRV-PI01 | 192.168.1.60 | Raspberry Pi |
| CLI-W11-01 | DHCP | Windows Client |
| CLI-LNX-01 | DHCP | Linux Client |

---

## Future VLANs

| VLAN | Name | Subnet |
|---------|----------------|----------------|
| 10 | Management | 192.168.10.0/24 |
| 20 | Servers | 192.168.20.0/24 |
| 30 | Clients | 192.168.30.0/24 |
| 40 | IoT | 192.168.40.0/24 |
| 50 | Lab | 192.168.50.0/24 |
| 99 | Native | 192.168.99.0/24 |