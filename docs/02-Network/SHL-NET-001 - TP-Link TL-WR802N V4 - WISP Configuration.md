# SHL-NET-001 - TP-Link TL-WR802N V4 Configuration (WISP Mode)

---

# 01 - Document Information

| Field | Value |
|-------|-------|
| Document ID | SHL-NET-001 |
| Title | Configuration of the TP-Link TL-WR802N V4 in WISP Mode |
| Category | Network |
| Criticality | Medium |
| Estimated Time | 15 min |
| Version | 1.0 |
| Status | Validated |
| Author | Sanjiexe |
| Creation Date | 28/06/2026 |
| Last Update | 28/06/2026 |
| Tags | TP-Link, WR802N, Wi-Fi, Ethernet, Proxmox |

---

# 02 - Objective

Configure the TP-Link TL-WR802N V4 nano router in **WISP Mode** to convert a wireless connection into an Ethernet connection for the **Sanji Homelab** infrastructure through **SW-01**.

---

# 03 - Context

The Sanji Homelab infrastructure cannot be connected directly to the ISP router using an Ethernet cable.

The TP-Link TL-WR802N V4 is configured in **WISP Mode** to connect to the home Wi-Fi network and provide wired network access to the homelab through the main switch (**SW-01**).

---

# 03.5 - Prerequisites

- TP-Link TL-WR802N V4 powered (5V / 1A)
- Administration workstation
- Ethernet cable (RJ45)
- Access to the home Wi-Fi network
- SSID
- Wi-Fi password
- Modern web browser
- Administrator access to the WR802N

---

# 04 - Hardware

| Component | Role | IP / FQDN | OS / Version |
|------------|--------------------------|-----------|----------------|
| TP-Link TL-WR802N V4 | Wi-Fi to Ethernet Bridge | DHCP | TP-Link Firmware |
| ISP Router | Internet Access | DHCP | ISP Firmware |
| Administration Workstation | Device configuration | DHCP | Windows 11 |

---

# 05 - Network Diagram

> Insert the network diagram here.

```text
                    Internet
                        │
                 ISP Router (Wi-Fi)
                        │
                     Wireless
                        │
               NRO-01 (WR802N V4)
                  WISP Mode
                        │
                    Ethernet
                        │
               SW-01 (TP-Link Omada)
           ┌────────┬────────┬────────┐
           │        │        │
        FW-01   SRV-HV01  SRV-PI01
```

---

# 06 - Procedure

## Step 1 - Preparation

- Power on the WR802N.
- Connect the administration workstation.
- Open a web browser.
- Access the administration interface.

```
http://tplinkwifi.net
```

or

```
http://192.168.0.1
```

---

## Step 2 - Configuration

- Log in to the administration interface.
- Select **WISP Mode**.
- Configure the WAN interface (Static IP or Dynamic IP according to your environment).
- Select the home Wi-Fi network from the AP List.
- Enter the Wi-Fi password.
- Save the configuration.

---

## Step 3 - Apply Configuration

- Apply the configuration.
- Reboot the WR802N if required.
- Connect the Ethernet cable to **SW-01**.
- Verify that connected devices receive network connectivity.
- Test Internet access.

---

# 07 - Verification

| Test | Action | Expected Result |
|------|--------|----------------|
| WR802N Login | Access Web Interface | Interface accessible |
| Wi-Fi Connection | Status = Connected | Connected |
| IP Address | Verify assigned address | Valid IP Address |
| Internet Access | `ping 8.8.8.8` | Replies received |
| DNS Resolution | `ping google.com` | Hostname resolved |

---

# 08 - Troubleshooting

| Symptom | Possible Cause | Solution |
|----------|----------------|----------|
| Cannot access the Web Interface | Incorrect IP address | Verify gateway or reset the device |
| No Wi-Fi networks detected | Out of range | Move closer to the ISP router |
| No Internet access | Incorrect Wi-Fi password | Reconfigure the wireless connection |
| No IP address assigned | DHCP issue | Verify network configuration |

---

# 09 - Rollback

If the deployment fails:

1. Hold the **RESET** button for approximately 10 seconds.
2. Wait for the router to reboot.
3. Restore the factory configuration.
4. Reconfigure the device.

---

# Risk Assessment

| Risk | Impact | Mitigation |
|------|--------|------------|
| Incorrect WISP configuration | Medium | Verify the selected operating mode before applying changes. |
| Incorrect Wi-Fi password | Low | Verify the SSID and password before saving. |
| Accidental factory reset | Medium | Document the configuration and back up the settings if possible. |
| Power interruption during configuration | Medium | Use a stable power source. |
| Temporary network outage | Medium | Perform changes during maintenance and validate connectivity immediately afterwards. |

---

# 10 - Conclusion

The TP-Link TL-WR802N V4 has been successfully configured in **WISP Mode**.

It now provides wired network connectivity to the **Sanji Homelab** infrastructure through **SW-01**, allowing future deployment of **SRV-HV01 (Proxmox)**, **FW-01**, and **SRV-PI01**.

---

# 11 - Revision History

| Version  | Date       | Author   | Description               |
|----------|------------|----------|---------------------------|
| 1.0      | 28/06/2026 | Sanjiexe | Initial document creation |
| 1.1 | | | |
| 1.2 | | | |

---

**Document generated by the Sanji Homelab Documentation System**
