# Metasploitable 2 Practice Lab (VirtualBox)

## Overview

This project documents the setup and initial exploitation of a local penetration testing lab using:

- **VirtualBox**
- **Kali Linux (Attacker)**
- **Metasploitable 2 (Target)**
- **Host-Only Network (Isolated Lab Environment)**

The goal of this lab was to practice:
- VM configuration
- Network isolation
- Service enumeration
- Basic exploitation techniques

---

## Lab Environment

| Component        | Configuration |
|------------------|--------------|
| Host OS          | Windows |
| Hypervisor       | Oracle VirtualBox |
| Attacker VM      | Kali Linux |
| Target VM        | Metasploitable 2 |
| Network Type     | Host-Only Adapter |

---

## 1. Downloaded Metasploitable 2

- Downloaded from official SourceForge:
  - `metasploitable-linux-2.0.0.zip`
- Extracted archive
- Located required disk file:
  - `Metasploitable.vmdk`

---

## 2. Created Metasploitable VM

VirtualBox configuration:

- Name: `Metasploitable2`
- Type: Linux
- Distribution: Ubuntu
- Version: Ubuntu (32-bit)
- RAM: 1024 MB
- Storage: Used existing virtual hard disk
  - Attached `Metasploitable.vmdk`

---

## 3. Configured Isolated Network

- Created Host-Only Adapter via:
  - `Tools → Network`
- Set both Kali and Metasploitable:
  - Adapter 1 → Host-Only Adapter

This ensures the vulnerable VM is **not exposed to the internet**.

---

## 4. Booted and Retrieved Target IP

Logged into Metasploitable:
---

## Screenshots

### Target IP Discovery
![Target IP](screenshots/01-ifconfig.png)

### Nmap Service Enumeration
![Nmap Scan](screenshots/02-nmap-scan.png)

### Root Shell Access
![Root Shell](screenshots/03-root-shell.png)

### Root Verification
![Root Proof](screenshots/04-root-proof.png)
