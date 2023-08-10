---
layout: post
title: Cortex-M Architecture
date: 2023-08-09 17:39:00
description: The ArmCortex-M3 microcontroller architecture follows the Harvard architecture design, separating memory into distinct areas for instructions and data.
tag: embedded
---
The ArmCortex-M3 microcontroller architecture follows the Harvard architecture design, separating memory into distinct areas for instructions and data. This allows for simultaneous access to both instruction memory and data memory, leading to improved performance. 

{% include figure.html path="assets/img/system_architecture_stm32.png" title="System architecture of STM32F1x Series"  %}

The Cortex-M instruction set includes the "Thumb" instruction set, which is a 16-bit compact encoding of instructions. This allows for more instructions to fit into a smaller memory space. Thumb-2 further extends this concept, allowing a mix of 16-bit and 32-bit instructions for better code density and performance.

The Cortex-M3 microcontroller architecture employs distinct buses and features for different tasks, contributing to its efficient operation in embedded systems:

1. **ICode Bus**: This bus is responsible for fetching instructions from memory, typically from a flash ROM. This is the pathway through which the processor retrieves program code for execution.
2. **DCode Bus**: The DCode bus is used for debugging purposes. It provides a pathway for advanced debugging features, allowing developers to interact with and analyze the behavior of the microcontroller during program execution.
3. **System Bus Interface**: The system bus interface facilitates data exchange between the processor core and memory, as well as input/output (I/O) devices. It's a critical bus for moving data around in the system.
4. **DMA (Direct Memory Access)**: DMA is a mechanism that allows certain peripherals to directly access memory without involving the processor core. This enhances data transfer efficiency and offloads the CPU from managing data movement.
5. **AHB (Advanced High-performance Bus)**: AHB is a high-performance bus protocol used to connect faster components in the system, like memory blocks, high-speed I/O (USB, Ethernet), and so on. It's designed to handle higher bandwidth and provide better performance.
6. **APB (Advanced Peripheral Bus)**: APB is a slower peripheral bus protocol used to connect slower peripherals in the system. It's used for components that don't require high-speed access and is more power-efficient.

## Registers

Registers are small fast storage areas within the CPU that are used to hold data temporarily during program execution. They are integral to various aspects of the processor's functioning, such as data manipulation, control flow, and interaction with memory and peripherals.

{% include figure.html path="assets/img/core_registers.JPG" title="Core Registers"  %}

The Core registers found in Arm microcontrollers are:

1. **General-Purpose Registers (GPRs)**: R0-R12 are 32-bit general-purpose registers for data operations. These registers are used for general data manipulation. They store operands for arithmetic and logical operations, intermediate results, and function parameters.
2. **Stack Pointer (SP)**: The SP (R13) register points to the top of the stack in memory. The stack is used to store temporary data during function calls, interrupt handling, and other operations. In Thread mode, bit[1] of the CONTROL register indicates the stack pointer to use:
    - 0 = *Main Stack Pointer* (MSP). This is the reset value.
    - 1 = *Process Stack Pointer* (PSP).
    
    On reset, the processor loads the MSP with the value from address `0x00000000`.
    
3. **Link Register (LR)**: The LR (R14) register holds the return address for subroutines, function calls, and exceptions. It's used to ensure that the program knows where to resume execution after the function call is complete. On reset, the processor sets the LR value to `0xFFFFFFFF.`
4. **Program Counter (PC)**: The PC (R15) register holds the address of the next instruction to be fetched and executed. It keeps track of the program's execution progress. On reset, the processor loads the PC with the value of the reset vector, which is at address `0x00000004`. Bit[0] of the value is loaded into the EPSR T-bit at reset and must be 1.
5. **Program Status Registers (PSR)**: The *Program Status Register* (PSR) combines:
    - *Application Program Status Register* (APSR)
    - *Interrupt Program Status Register* (IPSR)
    - *Execution Program Status Register* (EPSR).
    
    These registers hold various flags and status information about the processor's state. For example, they store the condition codes after arithmetic operations and control the processor's execution mode.
    
    These registers are mutually exclusive bitfields in the 32-bit PSR. The bit assignments are:
    

{% include figure.html path="assets/img/program_status_register.JPG" title="Program Status Registers"  %}

The key components stored in the APSR:

1. **Negative Flag (N) - Bit [31]**: This flag is set if the result of a signed operation is negative.
2. **Zero Flag (Z) - Bit [30]**: This flag is set if the result of an operation is zero. It's used in conditional branching and testing.
3. **Carry or Unsigned Overflow Flag (C) - Bit [29]**: This flag is set if an operation generates a carry out from the most significant bit or an unsigned overflow condition.
4. **Overflow Flag (V) - Bit [28]**: This flag is set if a signed operation results in an overflow condition.
5. **Q Flag - Bit [27]**: It's used in the context of saturation arithmetic (like Saturating Addition and Saturating Subtraction instructions).
1. **Exception Mask Registers:** The exception mask registers disable the handling of exceptions by the processor. Disable exceptions where they might impact on timing critical tasks.
    1. **Priority Mask Register (PRIMASK):** The PRIMASK register prevents activation of all exceptions with configurable priority. Bit [0] of this register controls the activation of exceptions. Its behavior is as follows:
        - 1 = prevents the activation of all exceptions with configurable priority.
        - 0 = no effect
    2. **Fault Mask Register (FAULTMASK):** The FAULTMASK register prevents activation of all exceptions except for *Non-Maskable Interrupt* (NMI). 
        - 1 = prevents the activation of all exceptions except for NMI.
        - 0 = no effect
    3. **Base Priority Mask Register (BASEPRI):** It is a special register used to control the priority level at which interrupts can preempt the currently executing code. It provides a mechanism for setting a "base" priority level below which certain interrupts will not preempt the execution of code at higher priority levels. Bit [7:0] of this register controls the behavior as follow:
        - 0x 00 = no effect
        - Nonzero = defines the base priority for exception processing. The processor does not process any exception with a priority value greater than or equal to BASEPRI.
        
        Suppose we set BASEPRI to a value of 3. This means that interrupts with priority levels 0, 1, and 2 can still interrupt the ongoing task. However, requests at priority levels 3 and higher will be held off temporarily. In other words, only the most important interrupts below the threshold will be allowed to break into the execution of the current task.
        
2. **CONTROL Register**: The CONTROL register controls the stack used and the privilege level for software execution when the processor is in Thread mode. The CONTROL register bit **assignments are:

| Bits | Name | Function |
| --- | --- | --- |
| [31:2] | - | Reserved. |
| [1] | SPSEL | Defines the currently active stack pointer: In Handler mode this bit reads as zero and ignores writes. The Cortex-M3 updates this bit automatically on exception return.
0 = MSP is the current stack pointer
1 = PSP is the current stack pointer. |
| [0] | nPRIV | Defines the Thread mode privilege level:
0 = Privileged
1 = Unprivileged. |

**Additional Resources:**

[Cortex-M3 Devices Generic User Guide](https://developer.arm.com/documentation/dui0552/a/the-cortex-m3-processor/programmers-model/core-registers?lang=en)