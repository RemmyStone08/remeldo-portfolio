# Packard Bell Laptop — Wi-Fi and Bluetooth Troubleshooting

## Overview
This case documents the troubleshooting of unstable Wi-Fi and disabled Bluetooth functionality on a Packard Bell laptop.

## Problem
The laptop showed inconsistent wireless behavior:
- Wi-Fi appeared in Windows but could not detect nearby networks
- Bluetooth was completely disabled
- The issue seemed to return after shutdowns or after driver-related changes

## Objective
Determine whether the fault was caused by drivers, the wireless adapter, Windows settings, or a deeper firmware-level issue.

## Device
- Brand: Packard Bell
- Affected components: Wi-Fi and Bluetooth wireless chip
- Environment: Windows laptop with intermittent wireless functionality

## Troubleshooting Process
### 1. Verified adapter visibility
- Confirmed the wireless adapter was visible in Windows
- Noted that functionality was inconsistent rather than fully absent

### 2. Investigated driver-related causes
- Checked Device Manager for adapter status
- Reinstalled and adjusted wireless drivers
- Used driver-update tools during testing

### 3. Tested whether the fix would hold
- Observed that software-based fixes appeared to help temporarily
- Confirmed that the issue returned after further use or restart

### 4. Expanded the scope of diagnosis
- Investigated beyond Windows and driver-level causes
- Considered firmware and BIOS-level control as a possible factor

## Findings
- The wireless chip was still being detected by the system
- Driver changes did not create a lasting fix
- The recurring behavior pointed away from a simple software issue

## Root Cause
A BIOS setting was disabling the Wi-Fi and Bluetooth chip, which created symptoms that looked like a driver or hardware fault.

## Resolution
Identified and corrected the BIOS setting responsible for disabling the wireless chip.

## Result
- Wi-Fi and Bluetooth functionality returned properly
- The laptop was repaired without replacing the wireless card
- A hardware workaround, such as a Wi-Fi dongle, was unnecessary

## Skills Demonstrated
- Wireless troubleshooting
- Driver and Device Manager investigation
- BIOS-level fault identification
- Hardware-versus-software fault isolation
- Practical repair decision-making

## Key Lesson
Not all wireless issues are caused by bad drivers or failed hardware. BIOS and firmware settings can create misleading symptoms and should be checked when software fixes do not hold.
