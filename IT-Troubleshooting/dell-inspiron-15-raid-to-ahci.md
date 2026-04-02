# Dell Inspiron 15 RAID to AHCI Conversion

## Overview
This case documents the safe conversion of a Dell Inspiron 15 from RAID mode to AHCI mode without breaking the existing Windows installation.

## Problem
The laptop was configured with RAID mode enabled in BIOS even though no RAID array was in use. This added unnecessary storage overhead and could limit SSD performance.

## Objective
Switch the storage controller from RAID to AHCI while keeping the system stable and bootable.

## Device
- Model: Dell Inspiron 15
- Storage: SATA SSD
- Original BIOS mode: RAID On
- Target BIOS mode: AHCI

## Risk
Changing storage mode directly in BIOS can cause Windows to fail to boot with `INACCESSIBLE_BOOT_DEVICE` if the correct driver is not prepared first.

## Troubleshooting Process
1. Opened Command Prompt as Administrator.
2. Enabled Safe Mode boot:
   ```cmd
   bcdedit /set safeboot minimal
   ```
3. Restarted and entered BIOS using `F2`.
4. Navigated to **SATA Operation**.
5. Changed **RAID On** to **AHCI**.
6. Saved settings and exited BIOS.
7. Allowed Windows to boot into Safe Mode.
8. Opened Command Prompt as Administrator again.
9. Disabled Safe Mode boot:
   ```cmd
   bcdedit /deletevalue safeboot
   ```
10. Restarted the system normally.

## Root Cause
The issue was not a hardware fault. The system was simply configured with RAID mode enabled by default, despite not using a RAID array.

## Resolution
Used the Safe Mode method to prepare Windows for the storage driver change before switching the BIOS setting from RAID to AHCI.

## Result
- Windows booted successfully after the change
- The system remained stable and usable
- The storage controller was switched without requiring an OS reinstall
- The laptop was better aligned for direct AHCI operation

## Skills Demonstrated
- BIOS configuration
- Windows boot troubleshooting
- Storage controller migration
- Safe Mode recovery workflow
- Risk prevention during system changes

## Key Lesson
Many consumer laptops ship with RAID enabled by default even when no actual RAID array is being used. Storage-mode changes should be handled carefully to avoid unnecessary boot failures.
