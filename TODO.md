1. Bug: `EIF_PRINTF` is masking a watchpoint that follows immediately after.

It appears that the app resumes on the target before EDB is listening for watchpoints.

1. Simultaneous printf and watchpoint streaming
    
Potential plan: split console into daemon and multiple clients, the CLI will be
one client, and various stream viewers can be other clients.

2. Flashing target, by adding a bootloader 

Use the UART connection between EDB and target. Should not
need any hardware modification to EDB.
