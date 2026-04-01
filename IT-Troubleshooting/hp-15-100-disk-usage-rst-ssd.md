# 100% Disk Usage on HP 15 (Intel RST + Budget SSD)

## Overview
This case documents the troubleshooting of persistent 100% disk usage on an HP 15 laptop, even after a clean Windows installation.

## Problem
The system consistently showed:
- 100% disk usage in Task Manager
- Very low read and write speeds
- Noticeable lag, freezing, and poor responsiveness

The same behavior remained even after reinstalling Windows and testing the SSD in another system.

## Objective
Determine whether the issue was caused by Windows, drivers, SSD health, BIOS restrictions, or a hardware compatibility limitation.

## Device
- Model: HP 15-da2xxx series
- Storage: Patriot P220 512GB SSD
- Storage mode: Intel RST (RAID, BIOS locked)
- Operating system: Windows 10/11

## Troubleshooting Process
### 1. Verified the symptom
- Used Task Manager to confirm 100% active time
- Noted low throughput despite high usage

### 2. Checked BIOS limitations
- Confirmed the system was locked to Intel RST mode
- Verified that no AHCI option was available

### 3. Tested the operating system separately
- Installed Windows on the SSD using another system
- Reinstalled the SSD into the HP laptop
- Observed that performance worsened because of platform and driver mismatch

### 4. Verified SSD condition
- SSD health was approximately 88%
- Power-on time was roughly 71 days
- No direct signs of SSD failure were present

### 5. Investigated the storage driver path
- Confirmed the Intel RST controller was in use
- Attempted driver reset and reinstall steps during testing

### 6. Applied temporary optimizations
- Disabled SysMain
- Disabled Windows Search
- Reduced unnecessary background activity

## Findings
- The SSD was functional but underperforming
- Intel RST introduced extra overhead and latency
- The budget SSD controller struggled under this storage setup
- The issue was not primarily caused by Windows itself

## Root Cause
The main limitation came from the combination of:
- Intel RST storage mode locked at firmware level
- A low-end DRAM-less SSD controller that performed poorly under that configuration

## Resolution
### Permanent recommendation
Replace the SSD with a stronger SATA model better suited to the platform, such as:
- Crucial MX500
- Samsung 870 EVO
- WD Blue SA510

### Temporary mitigation
- Disable SysMain
- Disable Windows Search
- Minimize background processes

## Result
- The system became more stable after optimization
- The real bottleneck was identified correctly
- A hardware upgrade path was recommended for full resolution

## Skills Demonstrated
- Performance troubleshooting
- Storage system analysis
- BIOS limitation diagnosis
- Hardware-versus-software fault isolation
- Client communication and recommendation

## Key Lesson
SSD health does not always reflect real-world performance. Controller quality and system compatibility matter, especially in systems locked to Intel RST mode.
