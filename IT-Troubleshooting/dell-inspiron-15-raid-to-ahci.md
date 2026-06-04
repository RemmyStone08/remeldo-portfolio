# RAID to AHCI Conversion — Dell Inspiron 15

**Device:** Dell Inspiron 15

**Symptom:** Poor SSD performance following HDD to SSD upgrade performed by a previous technician

**Outcome:** Full AHCI mode enabled — SSD performing as intended

---

## Client Report

The client returned to the store after a previous visit where another technician had upgraded his storage from an HDD to an SSD. Despite the upgrade, the system was not performing as expected.

---

## Observation

On inspection I identified that the system was still configured in RAID mode in the BIOS — a default configuration that appears on certain laptops even when no RAID array is present. This is a known issue on some Dell Inspiron models where the factory BIOS defaults to RAID rather than AHCI regardless of the storage configuration.

The problem with this is that RAID mode places demands on the storage device that many consumer SSDs are not designed to handle. The OS effectively requests full RAID-level usage from a drive that isn't built for it, resulting in degraded performance and in some cases instability.

---

## Process

Switching directly from RAID to AHCI in the BIOS without preparation causes Windows to fail to boot — the OS loses access to the storage controller. The correct process requires preparation before the BIOS change is made.

**Steps taken:**

1. Booted the system into Safe Mode
2. Removed the RAID drivers from within Safe Mode to allow Windows to fall back to basic storage drivers
3. Rebooted and entered the BIOS
4. Changed the storage configuration from RAID to AHCI
5. Booted back into Windows — the OS detected the AHCI controller correctly and loaded the appropriate drivers automatically

---

## Root Cause

The system was left in RAID mode following the original SSD installation. The previous technician completed the hardware swap without verifying or correcting the BIOS storage configuration, leaving the SSD running in an unsupported mode.

---

## Outcome

AHCI mode successfully enabled. SSD performance restored to expected levels. No data loss occurred during the conversion process.

---

## Key Learnings

- Always verify BIOS storage configuration after an SSD upgrade, not just the hardware installation itself.
- Some Dell Inspiron models default to RAID in the BIOS even without a RAID array — this is easy to miss if you're not looking for it.
- The Safe Mode driver removal step is critical. Attempting to switch directly from RAID to AHCI without it will result in a non-booting system.
- Consumer SSDs are not designed for RAID workloads. Leaving a system in this configuration causes unnecessary wear and performance degradation on the drive.

---

*Documented by Remeldo Stone — IT Technician, Matrix Warehouse*
