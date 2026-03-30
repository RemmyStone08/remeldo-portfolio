# Gaming PC No Display After Case Transfer

## Situation
A client’s gaming PC stopped displaying video immediately after a case transfer. The system powered on and the fans spun normally, but there was no POST screen or display output. The machine had been working before the rebuild, so the issue appeared to be introduced during reassembly.

## Task
My goal was to isolate the cause of the no-display condition quickly and methodically so I could determine whether the issue was related to assembly, power delivery, RAM, CPU contact, GPU, or motherboard failure.

## Action
I approached the fault as a structured hardware diagnostic job and worked through the most likely rebuild-related causes first.

### Step 1: Verified power and rebuild connections
- Checked the 24-pin motherboard power connection
- Checked the 8-pin CPU power connection
- Confirmed the correct CPU power cable was being used
- Rechecked major internal cables after the transfer

### Step 2: Eliminated the GPU as a variable
- Removed the dedicated GPU
- Used the motherboard display output instead
- Leveraged the Intel Core i9-14900K integrated graphics for testing

### Step 3: Investigated memory-related causes
- Reseated the RAM
- Planned single-stick testing in the primary DIMM slot
- Treated RAM initialization and training as possible no-POST causes

### Step 4: Checked CPU and socket condition
- Inspected the CPU seating
- Examined the LGA1700 socket pins for visible damage
- Found no obvious bent pins or visible socket defects

### Step 5: Ruled out case shorting
- Removed the motherboard from the case
- Performed an outside-the-case bench test with minimum hardware
- Confirmed the system still failed to POST outside the chassis

### Step 6: Continued board-level diagnostics
- Identified the **JBAT1** header for CMOS clearing
- Checked the board layout for further diagnostic points
- Narrowed the likely fault area to motherboard-side initialization, CPU contact/cooler pressure, or RAM initialization

### Step 7: Managed client communication
- Kept the client informed during diagnosis
- Explained that the fault had been narrowed down without making premature claims
- Balanced technical troubleshooting with deadline pressure

## Result
The troubleshooting process ruled out several common causes, including:
- Case shorting
- Dedicated GPU as the primary fault
- Obvious socket pin damage
- Basic power-up failure

By the end of the diagnostic stage, the strongest remaining suspects were:
1. Motherboard-side initialization failure
2. CPU contact or cooler pressure issue
3. RAM initialization problem

This job demonstrated a structured and professional approach to hardware diagnosis under time pressure, while also maintaining clear communication with the client about risk and next-step options.

## Skills Demonstrated
- Desktop hardware troubleshooting
- No-display / no-POST diagnosis
- Bench testing outside the case
- GPU elimination testing
- Integrated graphics fallback testing
- CPU and socket inspection
- CMOS reset point identification
- Logical fault isolation
- Client communication under deadline pressure

## Key Lesson
When a PC fails immediately after a rebuild or case transfer, the fault is not always a dead component. Assembly-related issues such as cooler pressure, motherboard contact, RAM initialization, or power connection problems must be ruled out systematically before declaring the motherboard failed.
