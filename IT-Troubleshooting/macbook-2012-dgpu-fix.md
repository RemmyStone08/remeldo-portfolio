# MacBook Pro 2012 — Dedicated GPU Failure

**Device:** MacBook Pro 15-inch Mid 2012
**Symptom:** Black screen during boot despite signs that the system was still running
**Outcome:** Restored functionality by forcing the system to use integrated graphics

---

## Client Report

The client reported that the MacBook would power on but never display an image. The screen remained black throughout startup, making the machine appear completely dead.

---

## Initial Assessment

During testing I noticed several indicators that the system was still functioning:

- Keyboard backlight activated
- Startup sounds were present
- Caps Lock responded normally
- Cooling fans behaved as expected

These signs suggested that the operating system was still loading, even though no image was being displayed.

---

## Device Information

- Model: MacBook Pro 15-inch Mid 2012
- Integrated Graphics: Intel HD Graphics 4000
- Dedicated Graphics: NVIDIA GeForce GT 650M

This model is known for graphics-related failures because it automatically switches between integrated and dedicated graphics depending on workload.

---

## Investigation

I initially considered several possibilities:

- Failed LCD panel
- Faulty display cable
- Corrupt operating system
- Logic board fault
- Graphics processor failure

Testing revealed that the machine remained operational despite having no display output. This pointed away from a complete motherboard failure and toward the graphics subsystem.

Further research into the model revealed a common fault involving the NVIDIA GT 650M dedicated graphics processor.

---

## Root Cause

The MacBook was attempting to initialise the dedicated NVIDIA GPU during startup.

Because the GPU had failed, the system could not successfully complete graphics initialisation, resulting in a black screen even though the remainder of the computer continued operating normally.

---

## Resolution

To restore functionality, I forced the system to use the Intel HD 4000 integrated graphics processor instead of the failed NVIDIA GPU.

This was accomplished through macOS recovery tools and NVRAM configuration changes that prevented the dedicated GPU from being selected during boot.

### Recovery Command Used

```bash
nvram fa4ce28d-b62f-4c99-9cc3-6815686e30f9:gpu-power-prefs=%01%00%00%00
reboot
```

---

## Result

- Display functionality restored
- System booted successfully
- Client regained access to files and applications
- No replacement parts required

---

## Limitations

This repair is a workaround rather than a permanent hardware repair.

The failed dedicated GPU remains present on the logic board and certain firmware resets may cause the issue to reappear.

---

## Permanent Repair Options

- Disable the dedicated GPU power rail
- Implement an OpenCore-based GPU block
- Replace the logic board

---

## Key Learnings

- A black screen does not always indicate a dead computer.
- Observing system behaviour can provide valuable diagnostic clues.
- Common model-specific faults should always be considered during troubleshooting.
- Understanding how integrated and dedicated graphics interact can significantly reduce diagnostic time.

---

*Documented by Remeldo Stone — IT Technician, Matrix Warehouse*