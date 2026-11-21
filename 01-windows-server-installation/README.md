# Project 01 — Windows Server 2022 Installation

<badge>Project 01</badge>

## 1. Overview

This project covers the installation and initial configuration of Windows Server 2022 Standard with Desktop Experience.

The goal is to build a Windows Server from scratch and prepare it to operate as the foundation of a small enterprise IT environment.

This server will eventually provide centralized user management, authentication, DNS, DHCP, file sharing, and Group Policy management.

**Project status:** Planned

## 2. Lab Environment

### Hardware

| Component | Configuration |
|---|---|
| Computer | MacBook Air Early 2014 |
| Processor | Intel |
| Memory | 8 GB RAM |
| Storage | Internal SSD |

### Software

| Component | Configuration |
|---|---|
| Operating System | Windows Server 2022 Standard |
| Installation Type | Desktop Experience |
| Administration | Server Manager |
| Command Line | Windows PowerShell |
| Future Directory Service | Active Directory Domain Services |

## 3. Project Objectives

By completing this project, I will demonstrate the ability to:

- Install Windows Server 2022.
- Configure the local Administrator account.
- Change the server hostname.
- Configure a static IPv4 address.
- Configure the default gateway and DNS settings.
- Install Windows updates.
- Verify network connectivity.
- Inspect network adapters and network configuration.
- Perform basic troubleshooting using PowerShell.

## 4. Planned Network Configuration

The server will use the following naming convention:

| Setting | Planned Value |
|---|---|
| Computer Name | SERVER01 |
| Server Role | Future Domain Controller |
| IPv4 Address | To be determined |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | To be determined |
| Preferred DNS | To be determined |

**Important:** Actual IP addresses must be selected based on the home network configuration. The server should have a reserved address that does not conflict with another device.

The DNS configuration will be updated when the DNS server role is installed in a later project.

## 5. Installation Procedure

The installation process will follow these steps:

1. Prepare Windows Server 2022 installation media.
2. Boot the computer from the installation media.
3. Select Windows Server 2022 Standard with Desktop Experience.
4. Accept the Microsoft software license terms.
5. Select the appropriate installation destination.
6. Complete the Windows installation.
7. Set the local Administrator password.
8. Sign in to Windows Server.
9. Open Server Manager.
10. Verify the installation.

## 6. Initial Server Configuration

### 6.1 Rename the Server

The server will be renamed to `SERVER01`.

PowerShell command:

```powershell
Rename-Computer -NewName "SERVER01" -Restart
```

The computer will restart after executing this command.

### 6.2 Verify the Hostname

```powershell
hostname
```

Expected result:

```text
SERVER01
```

### 6.3 Verify the Operating System

```powershell
Get-ComputerInfo | Select-Object WindowsProductName, WindowsVersion, OsBuildNumber
```

### 6.4 Inspect Network Configuration

```powershell
ipconfig /all
```

This command displays:

- Network adapter information.
- IPv4 and IPv6 addresses.
- Subnet mask.
- Default gateway.
- DHCP configuration.
- DNS servers.

### 6.5 Inspect Network Adapters

```powershell
Get-NetAdapter
```

This command displays the network adapters installed on the server and their connection status.

### 6.6 Inspect IP Configuration

```powershell
Get-NetIPConfiguration
```

This command provides a PowerShell overview of the server's network configuration.

## 7. Network Connectivity Tests

The following commands will be used to verify network connectivity.

### Test the Default Gateway

```powershell
ping 192.168.1.1
```

Replace the example address with the actual gateway address.

### Test Internet Connectivity

```powershell
ping 1.1.1.1
```

### Test DNS Resolution

```powershell
nslookup microsoft.com
```

### Test the Network Route

```powershell
tracert microsoft.com
```

The results of these tests will be documented after the server is configured.

## 8. Windows Updates

Windows Server should be updated before installing additional server roles.

Tasks:

- Check for available Windows updates.
- Install applicable updates.
- Restart the server if necessary.
- Check for additional updates.
- Record any errors encountered.

## 9. Security Considerations

Initial security practices:

- Use a strong Administrator password.
- Keep Windows Firewall enabled.
- Install security updates.
- Avoid using the built-in Administrator account for routine daily activities.
- Document administrative changes.
- Do not publish passwords, private IP details that reveal sensitive network information, or other credentials in this repository.

## 10. Verification Checklist

The following checklist will be completed during the project.

- [ ] Windows Server 2022 installed successfully.
- [ ] Administrator can sign in.
- [ ] Server hostname changed to SERVER01.
- [ ] Network adapter detected.
- [ ] Static IPv4 address configured.
- [ ] Subnet mask verified.
- [ ] Default gateway verified.
- [ ] DNS settings verified.
- [ ] Network connectivity tested.
- [ ] Windows updates installed.
- [ ] Server Manager verified.

## 11. Screenshots and Evidence

Screenshots will be stored in the `screenshots` subfolder.

| Screenshot | Evidence |
|---|---|
| 01 | Windows Server desktop |
| 02 | Server Manager dashboard |
| 03 | Windows Server version |
| 04 | Hostname verification |
| 05 | Network adapter information |
| 06 | IP configuration |
| 07 | Successful connectivity test |
| 08 | Windows Update status |

Screenshots will be added after the corresponding tasks have been completed.

## 12. Troubleshooting Log

Real problems encountered during the installation and configuration will be documented here.

Each troubleshooting report will include:

- Problem description.
- Symptoms.
- Diagnostic commands.
- Investigation steps.
- Root cause.
- Resolution.
- Verification.

No problems or resolutions will be presented as actual experiences until they have been tested.

## 13. Skills Demonstrated

This project develops practical skills in:

- Windows Server installation.
- Server configuration.
- Windows administration.
- IPv4 networking.
- PowerShell.
- Network troubleshooting.
- Windows security.
- Technical documentation.

## 14. Next Project

**Project 02 — Active Directory Domain Services**

The next project will cover:

- Installing the Active Directory Domain Services role.
- Installing and configuring DNS.
- Promoting SERVER01 to a Domain Controller.
- Creating an Active Directory domain.
- Verifying domain functionality.

---

**Portfolio:** Windows Enterprise Home Lab

**Project:** 01 — Windows Server 2022 Installation

**Status:** Planned
