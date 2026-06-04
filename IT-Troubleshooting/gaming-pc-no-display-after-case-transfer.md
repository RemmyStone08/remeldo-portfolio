# Gaming PC — No Display After Case Transfer

**Device:** Custom built gaming PC
**Symptom:** System would not boot following a case transfer
**Outcome:** Short circuit identified in front panel USB 3.0 cable — system restored to full operation

---

## Client Report

The client brought in a custom gaming PC that would not boot following a case transfer. The transfer had been described as standard with no known issues during the process.

---

## Initial Diagnosis

On inspection the system showed no signs of life — no display output, no POST. All components had been transferred from the original case and were seated correctly. The build itself appeared normal with no obvious signs of damage or misconnection.

---

## Process

I worked through the standard no boot checklist methodically:

- Verified power connections to the motherboard, CPU, and GPU
- Reseated the RAM
- Checked GPU seating and display cable connections
- Verified front panel header connections

With no obvious fault found through visual inspection I began disconnecting non-essential components to isolate the cause. When I disconnected the USB 3.0 front panel cable from the motherboard header the system booted immediately.

---

## Root Cause

The USB 3.0 cable running from the front IO ports of the new case had an internal short. When connected to the motherboard header it was pulling enough current to prevent the system from completing POST. The fault was not visible externally — the cable appeared undamaged.

---

## Outcome

System booted successfully with the faulty USB 3.0 front panel cable disconnected. The client was advised of the fault and the cable was replaced. Full functionality including front panel USB ports was restored after the replacement.

---

## Key Learnings

- Case accessories including front panel cables should be treated as potential fault points, not just the core components.
- A short in a front panel USB 3.0 cable can prevent a system from booting entirely — it is not always an obvious culprit in a no POST diagnosis.
- When a build appears correct but won't boot, systematically disconnecting non-essential peripherals and headers is an effective isolation technique.
- Case transfers introduce new variables even when the process seems straightforward. Always test with minimal connections before assuming a component fault.

---

*Documented by Remeldo Stone — IT Technician, Matrix Warehouse*