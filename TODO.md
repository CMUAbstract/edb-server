1. Bug: `EIF_PRINTF` is masking a watchpoint that follows immediately after.

It appears that the app resumes on the target before EDB is listening for watchpoints.

2. Bug: skipped watchpoints, with and without buffering.

This is likely due to DMA keeping the core busy. Need to switch to Xmos Xcore...

2. Simultaneous printf and watchpoint streaming
    
Potential plan: split console into daemon and multiple clients, the CLI will be
one client, and various stream viewers can be other clients.

3. libedb API for charging and discharging from within app

Add CHARGE()/DISCHARGE() calls, that would talk to EDB and have it
charge or discharge the capacitor to a given voltage.

4. Flashing target, by adding a bootloader 

Use the UART connection between EDB and target. Should not
need any hardware modification to EDB.

5. Precise energy and current measurement circuit

Incorporate a Coulomb counter for energy measurement and current measurement IC
(or instrumentation op amp + Rsense).
