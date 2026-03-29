# Packard Bell Laptop - Wi-Fi and Bluetooth Troubleshooting

## Issue
The laptop's Wi-Fi was unstable. At one stage, Wi-Fi appeared in Windows but could not detect nearby networks, and Bluetooth was completely disabled.

## Initial Observations
- The wireless adapter was visible in Windows
- Functionality was inconsistent
- The issue seemed to return after shutdown or after driver-related changes

## Troubleshooting Performed
- Checked Device Manager for the wireless adapter status
- Reinstalled and adjusted wireless drivers
- Used driver update tools during troubleshooting
- Verified that software changes did not permanently resolve the issue
- Investigated settings beyond Windows and driver-level fixes

## What Happened During Testing
A driver-related fix appeared to help temporarily, but the problem returned. That suggested the root cause was not only the driver package.

## Root Cause
The actual cause was a BIOS setting that kept disabling the Wi-Fi and Bluetooth chip.

## Resolution
After identifying and correcting the BIOS setting, Wi-Fi and Bluetooth functionality returned properly.

## Final Outcome
The laptop was successfully repaired without needing to replace the wireless card or rely on a Wi-Fi dongle as a workaround.

## Lesson Learned
This case reinforced the importance of checking firmware and BIOS-level settings when a device appears to have a driver or hardware fault. Not all wireless issues are caused by damaged hardware or bad drivers.
