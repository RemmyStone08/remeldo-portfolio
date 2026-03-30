# Dell Inspiron 15 RAID to AHCI Conversion

## Overview
This case documents the process of converting a Dell Inspiron 15 from RAID mode to AHCI mode in BIOS without causing Windows boot failure.

## Problem
The laptop was configured with RAID mode enabled in BIOS even though no RAID array was being used. This introduced unnecessary storage overhead and potential SSD performance limitations.

## Objective
Switch the storage controller from RAID to AHCI safely while keeping the existing Windows installation bootable.

## Device
- Model: Dell Inspiron 15
- Storage: SATA SSD
- Original BIOS Mode: RAID On
- Target BIOS Mode: AHCI

## Risk
Changing RAID to AHCI directly in BIOS can cause Windows to fail to boot with `INACCESSIBLE_BOOT_DEVICE`.

## Troubleshooting Process
1. Open Command Prompt as Administrator.
2. Enable Safe Mode boot:
   ```cmd
   bcdedit /set safeboot minimal
   ```
3. Restart and enter BIOS using `F2`.
4. Navigate to **SATA Operation**.
5. Change **RAID On** to **AHCI**.
6. Save and exit BIOS.
7. Allow Windows to boot into Safe Mode.
8. Open Command Prompt as Administrator again.
9. Disable Safe Mode boot:
   ```cmd
   bcdedit /deletevalue safeboot
   ```
10. Restart the system normally.

## Result
Windows successfully booted in AHCI mode without requiring an operating system reinstall.

## Outcome
- Storage controller switched successfully
- System remained stable and bootable
- Reduced dependency on the RAID storage layer

## Skills Demonstrated
- BIOS configuration
- Windows boot troubleshooting
- Storage controller migration

## Lesson Learned
Many consumer laptops ship with RAID enabled by default even when no actual RAID array is being used. Safely switching to AHCI requires preparing Windows first so the correct storage driver loads during the next boot.
