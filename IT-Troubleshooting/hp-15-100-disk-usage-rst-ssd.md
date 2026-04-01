# 100% Disk Usage on HP 15 (RST + Budget SSD)

## Overview
This case documents troubleshooting persistent 100% disk usage on an HP 15 laptop, even after a clean Windows installation.

## Problem
The system consistently showed:
- 100% disk usage in Task Manager
- Low read/write speeds
- System lag and freezing

This occurred even after reinstalling Windows and testing on another system.

## Device
- Model: HP 15-da2xxx series
- Storage: Patriot P220 512GB SSD
- Storage Mode: Intel RST (RAID, BIOS locked)
- OS: Windows 10/11

## Initial Symptoms
- Disk usage stuck at 100%
- Minimal data transfer (0–5 MB/s)
- System responsiveness severely affected

## Troubleshooting Process

### 1. Verified Disk Usage
- Used Task Manager to confirm 100% active time
- Identified low throughput despite high usage

### 2. Checked BIOS Configuration
- Confirmed system locked to Intel RST mode
- No AHCI option available

### 3. Tested Clean OS Installation
- Installed Windows on another system
- Moved SSD back to HP laptop
- Performance worsened due to driver mismatch

### 4. Verified SSD Health
- Health: ~88%
- Power-on time: ~71 days
- No signs of failure

### 5. Driver Investigation
- Confirmed Intel RST controller in use
- Attempted driver reset and reinstall

### 6. System Optimization
- Disabled SysMain (Superfetch)
- Disabled Windows Search
- Reduced background processes

## Findings

- SSD was healthy but underperforming
- Intel RST added overhead and latency
- Budget SSD (DRAM-less) struggled under RST
- Issue was not software-related

## Root Cause
Performance limitation caused by:
- Intel RST storage mode (firmware-level restriction)
- Low-end SSD controller (Patriot P220)

## Solution

### Recommended (Permanent Fix)
- Replace SSD with higher-quality model:
  - Crucial MX500
  - Samsung 870 EVO
  - WD Blue SA510

### Temporary Fix
- Disable SysMain
- Disable Windows Search
- Reduce background applications

## Result
- System stabilized with optimizations
- Root cause identified as hardware limitation
- Upgrade recommended for full resolution

## Skills Demonstrated
- Performance troubleshooting
- Storage system analysis
- BIOS limitation diagnosis
- Differentiating hardware vs software issues
- Client communication and recommendation

## Lesson Learned
SSD health does not equal performance. Controller quality and system compatibility play a major role, especially in systems locked to Intel RST mode.
