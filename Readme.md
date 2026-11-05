# RISC-V 
Used for Instruction Set Architechture(ISA), it is a open source ISA, RISC-V Base Integer ISA was released in 2010 and has only 40 instructions.

## Naming convention for custom RISC-V ISA
consists of the letters RV (for RISC-V) followed by the bit-width, and then a series of 1-letter identifiers for the base ISA and its extensions.
RV32IMAC means:
- RV32I: A 32-bit CPU with the Base Integer ISA. This includes the absolutely necessary instructions for basic operation.
- M: The Integer Multiplication and Division extension.
- A: The Atomic Instruction extension.
- C: The Compressed Instruction extension. This extension provides an alternative 16-bit encoding for a special subset of existing RV321 instructions, which are encoded in 32 bits.
![RV32IMAC image](./assets/image.png)

## Organizing the specification
The RISC-V ISA is broken up into two parts:
- Volume 1, Unprivileged Specification
- Volume 2, Privileged Specification

unlike the x86 architechture where we have 4 ring, ring 0 kernel, ring 1 and 2 device drivers, ring 3 for application
<b>RISC-V has three privilege levels: User Mode (U-mode), Supervisor Mode (S-mode), and Machine Mode (M-mode). One can think of these as “Ring 2”, “Ring 1”, and “Ring 0” respectively. Other modes like a hypervisor mode (H-Mode) are available as variations of these 3 basic modes.</b>
U-mode is for user processes, S-mode is for kernel and/or device drivers, and M-mode is used for bootloader and/or firmware. Each privilege level has access to specific Control and Status Registers (CSRs), which are special registers that report the state of the system, or control its behavior. Higher privilege levels can access the CSRs of less privileged levels.
