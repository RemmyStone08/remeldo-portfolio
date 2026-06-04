# 100% Disk Usage Diagnosis — HP 15 (Intel RST + SSD)

**Device:** HP 15 laptop

**Symptom:** Constant 100% disk usage, severely degraded system performance

**Outcome:** Root cause identified and documented — hardware limitation prevented full resolution

---

## Client Report

The client came in complaining that their laptop was extremely slow and unresponsive. Task Manager was showing constant 100% disk usage even at idle.

---

## Initial Diagnosis

On inspection I identified that the system was configured in RAID mode in the BIOS, with Intel Rapid Storage Technology (RST) drivers active. An SSD had been installed in the system but the BIOS storage configuration had never been updated to match.

This mirrors a known issue where RAID mode places demands on the storage device that consumer SSDs are not designed to handle, causing the OS to continuously request full RAID-level usage from the drive and resulting in sustained 100% disk usage.

---

## Attempted Resolution

On the Dell Inspiron 15 I had previously resolved an identical configuration issue by booting into Safe Mode, removing the RAID drivers, and switching the BIOS from RAID to AHCI. I attempted to apply the same process here.

However on this HP 15 model, inspection of the BIOS revealed that there was no AHCI controller option available on the motherboard. The hardware simply did not support switching to AHCI mode, meaning the standard resolution path was not available.

---

## Root Cause

The SSD was installed without updating the BIOS storage configuration, leaving the system running in RAID mode with Intel RST active. Unlike some other models, this HP 15 motherboard lacked an AHCI controller entirely, making a full software resolution impossible without a hardware level intervention.

---

## Outcome

Full resolution was not possible within the constraints of the existing hardware. The case was documented and the client was advised of the hardware limitation. Options discussed included a motherboard replacement or accepting the performance constraints of the current configuration.

---

## Key Learnings

- Not all laptops support AHCI mode. Always check BIOS options before assuming a RAID to AHCI conversion is possible.
- The same symptom can have the same root cause but a different resolution path depending on the hardware.
- Knowing when a fix is not possible is just as important as knowing how to fix something. Documenting limitations protects both the technician and the client.
- Intel RST in combination with a consumer SSD on unsupported hardware is a recurring source of 100% disk usage issues worth checking early in any slow laptop diagnosis.

---

*Documented by Remeldo Stone — IT Technician, Matrix Warehouse*
