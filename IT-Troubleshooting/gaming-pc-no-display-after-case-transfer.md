# Gaming PC No Display After Case Transfer

## Overview
This case documents the diagnosis of a gaming PC that stopped displaying video immediately after a case transfer.

## Problem
The system powered on and the fans spun normally, but there was no POST screen and no display output. The PC had been working before the rebuild, which strongly suggested the fault had been introduced during reassembly.

## Objective
Quickly narrow the fault to the most likely area by testing power delivery, RAM, GPU, CPU contact, motherboard behavior, and possible assembly-related issues.

## Device
- Type: Custom gaming desktop
- CPU: Intel Core i9-14900K
- Graphics path used for testing: Dedicated GPU and integrated graphics
- Scenario: No-display/no-POST condition after case transfer

## Troubleshooting Process
### 1. Verified power and rebuild connections
- Checked the 24-pin motherboard power connection
- Checked the 8-pin CPU power connection
- Confirmed the correct CPU power cable was in use
- Rechecked major internal connections after the transfer

### 2. Removed the GPU as a primary variable
- Removed the dedicated GPU
- Switched testing to motherboard display output
- Used the CPU’s integrated graphics to reduce variables

### 3. Investigated memory-related causes
- Reseated the RAM
- Planned single-stick testing in the primary DIMM slot
- Treated memory training and RAM initialization as possible no-POST causes

### 4. Checked CPU seating and socket condition
- Inspected CPU seating
- Examined the LGA1700 socket for visible pin damage
- Found no obvious bent pins or visible socket defects

### 5. Ruled out case shorting
- Removed the motherboard from the case
- Performed a minimum-hardware bench test outside the chassis
- Confirmed the system still failed to POST

### 6. Continued board-level narrowing
- Identified the **JBAT1** header for CMOS clearing
- Reviewed the board layout for further diagnostic points
- Narrowed the remaining fault area to motherboard initialization, CPU contact or cooler pressure, or RAM initialization

### 7. Managed client communication
- Kept the client informed during testing
- Avoided making premature claims before enough evidence was gathered
- Balanced technical diagnosis with the client’s time pressure

## Findings
- Basic power-up was present
- The dedicated GPU was unlikely to be the sole cause
- Case shorting was ruled out
- No obvious socket damage was visible
- The fault remained within core system initialization

## Root Cause
At the end of the diagnostic stage, the issue had not yet been reduced to a single confirmed failed component. The strongest remaining suspects were:
1. Motherboard-side initialization failure
2. CPU contact or cooler pressure issue
3. RAM initialization problem

## Resolution
This case focused on structured fault isolation rather than an immediate final repair. The main outcome was narrowing the fault professionally and accurately without guessing.

## Result
- Several common rebuild-related causes were ruled out
- The fault area was narrowed significantly
- The client received a clear and honest diagnostic position
- The troubleshooting process remained methodical under deadline pressure

## Skills Demonstrated
- Desktop hardware troubleshooting
- No-display / no-POST diagnosis
- Bench testing outside the case
- GPU elimination testing
- Integrated graphics fallback testing
- CPU and socket inspection
- CMOS reset point identification
- Logical fault isolation
- Client communication under pressure

## Key Lesson
When a PC fails immediately after a rebuild or case transfer, the fault is not always a dead component. Assembly-related issues should be ruled out systematically before declaring a motherboard or CPU defective.
