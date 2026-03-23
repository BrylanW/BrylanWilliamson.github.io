# My First-Hour Priorities

## Overview
This document outlines my first-hour priorities during an incident response investigation, including what evidence I capture first, what actions I avoid, and how I preserve integrity and privacy throughout the process.

---

## What I Capture First

### Log Files and Volatile Memory
These are time-sensitive and can be lost quickly. They may contain evidence of active processes, attacker presence, or other indicators of compromise.

### System Time and Clock Drift
Accurate time data is essential for building a reliable investigation timeline.

### Running Processes and Open Network Connections
This helps identify suspicious activity, malware, persistence mechanisms, or lateral movement.

### External Device Connections or Mounted Volumes
These may indicate possible data exfiltration or a physical entry point for compromise.

---

## What I Avoid

### Rebooting or Patching Systems
This can destroy volatile data and alter the system state before evidence is collected.

### Making Forensic Changes Before Imaging
This helps preserve evidence integrity and supports legal admissibility.

---

## Incident and Evidence Note

On **September 10, 2025, at 1:45 PM ET**, I was alerted to abnormal outbound traffic originating from **host HR-PC-004**. Upon arrival, I captured a memory image using **FTK Imager** and verified it with a **SHA-256 hash**.

I documented:
- Running processes
- Network connections
- 48 hours of relevant system logs
- 48 hours of relevant application logs

No physical signs of tampering were found.

All evidence was transferred to secure storage at:

```text
/evidence/case-019/
