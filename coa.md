#  **UNIT I  : Basic Structure & Addressing**
## **Short Answers**

## **1. List and briefly define the main structural components of a computer.**

A computer system is composed of the following main structural components:

### 1. Central Processing Unit (CPU)

The CPU is the brain of the computer. It performs all arithmetic and logical operations and controls the execution of instructions. It consists of:

* **ALU (Arithmetic Logic Unit)** – Performs arithmetic and logical operations.
* **Control Unit (CU)** – Directs and coordinates all operations.
* **Registers** – Small high-speed storage locations inside CPU.

---

### 2. Main Memory

Main memory stores data and instructions currently being used by the CPU.
It is directly accessible by the processor.
Types include RAM and ROM.

---

### 3. Input Unit

This unit accepts data and instructions from the user.
It converts input into machine-readable form.

---

### 4. Output Unit

It presents processed results to the user in human-readable form.

---

### 5. System Interconnection (Bus)

All components are connected through buses that transfer data, address, and control signals.

---

## **2. What are the different types of buses used in computer architecture?**

A bus is a communication pathway used to transfer data between components.

### 1. Data Bus

* Transfers actual data between CPU, memory, and I/O devices.
* It is bidirectional.
* Width of data bus determines data transfer capacity.

---

### 2. Address Bus

* Carries address of memory location.
* It is unidirectional (from CPU to memory).
* Width determines maximum memory size.

---

### 3. Control Bus

* Carries control signals such as Read, Write, Interrupt, Clock.
* Coordinates operations of different components.

---

### Summary

| Bus Type    | Direction      | Purpose                   |
| ----------- | -------------- | ------------------------- |
| Data Bus    | Bidirectional  | Transfers data            |
| Address Bus | Unidirectional | Transfers address         |
| Control Bus | Both           | Transfers control signals |

---

## **3. Represent the following conditional control statement using control functions**

### Given Statement:

If (P = 1) then R1 ← R2
Else if (Q = 1) then R1 ← R3

---

### Control Function Representation:

Control functions use logical conditions to activate micro-operations.

[
P : R1 \leftarrow R2
]

[
\overline{P} \cdot Q : R1 \leftarrow R3
]

---

### Explanation:

* When **P = 1**, transfer R2 into R1.
* If **P = 0** and **Q = 1**, transfer R3 into R1.
* If both P and Q are 0, no transfer occurs.
* Here, ( \overline{P} ) ensures second operation happens only when first condition fails.

---

## **4. Addressing Modes**

### Definition

Addressing mode specifies how the operand of an instruction is obtained.

---

### Types of Addressing Modes

### 1. Immediate Addressing

Operand is directly given in instruction.
Example: `ADD R1, #5`
Fast but limited range.

---

### 2. Direct Addressing

Instruction contains memory address of operand.
EA = Address field.
Requires one memory access.

---

### 3. Indirect Addressing

Address field contains address of another memory location.
EA = M[Address].
Requires two memory accesses.

---

### 4. Register Addressing

Operand is stored in register.
Very fast.

---

### 5. Register Indirect Addressing

Register holds address of operand.

---

### 6. Indexed Addressing

EA = Address + Index Register
Used for arrays.

---

### Conclusion

Addressing modes improve flexibility, reduce instruction size, and support efficient memory usage.

---


## **Long Answers**

## **1. Common Bus System for 8 Registers (n-bit each)**

A digital computer has 8 registers, each of n bits, connected through a common bus using multiplexers.

### (i) Number of Select Inputs

To select one register out of 8 registers:
[
\text{Number of select lines} = \log_2 8 = 3
]

Therefore, **3 select inputs** are required in each multiplexer to choose one of the 8 registers.

---

### (ii) Size of Multiplexers Needed

Each bus line must select one bit from the same bit position of all 8 registers.

Thus, each multiplexer must be of size:

[
8 \times 1
]

That means:

* 8 input lines (from 8 registers)
* 1 output line (to bus)
* 3 select lines

---

### (iii) Number of Multiplexers in the Bus

Each register has **n bits**, and each bit position requires one multiplexer.

Therefore:

[
\text{Number of multiplexers} = n
]

So for n-bit registers:

* n multiplexers are required
* Each multiplexer is 8×1

---

### Conclusion

| Parameter     | Value |
| ------------- | ----- |
| Select Inputs | 3     |
| Size of MUX   | 8 × 1 |
| Number of MUX | n     |

This arrangement allows only one register to place its content on the bus at a time.

---

## **2. Functional Units of Computer System**

A computer system consists of five major functional units that work together to process information.

---

### 1. Input Unit

* Accepts data and instructions from user.
* Converts input into binary form.
* Sends data to memory or CPU.

---

### 2. Memory Unit

Stores data, instructions, and intermediate results.

Types:

* **Primary Memory (RAM, ROM)** – Directly accessible by CPU.
* **Secondary Memory** – Used for permanent storage.

Functions:

* Stores program before execution.
* Supplies instructions to CPU.
* Stores final results.

---

### 3. Central Processing Unit (CPU)

CPU is the brain of computer. It consists of:

#### (a) Arithmetic Logic Unit (ALU)

* Performs arithmetic operations (add, subtract, multiply).
* Performs logical operations (AND, OR, NOT, compare).

#### (b) Control Unit (CU)

* Directs all operations of computer.
* Fetches instructions from memory.
* Decodes instructions.
* Generates control signals.

#### (c) Registers

* Small high-speed storage locations.
* Examples: PC, IR, MAR, MDR, Accumulator.

---

### 4. Output Unit

* Displays processed results to user.
* Converts binary results to human-readable form.

---

### 5. System Bus

* Connects CPU, memory, and I/O devices.
* Transfers data, address, and control signals.

---

### Conclusion

All functional units coordinate through control signals to perform the instruction cycle efficiently.

---

## **3. BUS Arbitration**

### Definition

Bus arbitration is the process of deciding which device gets control of the system bus when multiple devices request it simultaneously.

---

### Why It Is Needed

* Prevents data collision.
* Avoids bus contention.
* Ensures orderly data transfer.
* Maintains system stability.

Without arbitration, multiple devices may try to use bus at same time causing system failure.

---

### Daisy Chaining Scheme

In daisy chaining, devices are connected in serial priority order.

![Image](https://www.tutorialspoint.com/assets/questions/media/14987/centralized_bus_arbitration.jpg)

![Image](https://files.transtutors.com/book/qimg/1db115a4-21db-4c1c-afc3-02363dd049d5.png)

![Image](https://files.codingninjas.in/article_images/custom-upload-1677928461.webp)

![Image](https://www.researchgate.net/publication/245562673/figure/fig2/AS%3A385570166591489%401468938499284/Control-diagram-of-bus-signal-priority-strategy.png)

### Working

* CPU sends Bus Grant signal.
* Grant signal passes through devices sequentially.
* First requesting device captures grant.
* Other devices wait.

---

### Advantages

* Simple implementation.
* Low hardware cost.

### Disadvantages

* Fixed priority system.
* Low priority devices may starve.

---

## **4. Multiple Bus Organization**

In single bus organization, only one data transfer occurs at a time, creating bottleneck.

To overcome this, multiple bus architecture is used.

![Image](https://upload.wikimedia.org/wikipedia/commons/c/c9/Three_bus_organization.jpg)

![Image](https://www.expertsmind.com/CMSImages/389_Multiple%20bus%20architecture.png)

![Image](https://www.researchgate.net/publication/221239685/figure/fig1/AS%3A669081355165716%401536532834248/Block-diagram-of-the-implemented-processor-with-register-file-ALU-data-memory-and.png)

![Image](https://cs.stanford.edu/people/eroberts/courses/soco/projects/2005-06/64-bit-processors/microprocessor.gif)

---

### Structure

Typically three buses are used:

* **Bus A** – Carries first operand
* **Bus B** – Carries second operand
* **Bus C** – Carries result

Registers connect to Bus A and Bus B as input to ALU.
ALU output goes to Bus C.

---

### Working

1. Two registers place data on Bus A and Bus B simultaneously.
2. ALU performs operation.
3. Result transferred to destination register via Bus C.

---

### Advantages

* Parallel data transfer.
* Faster execution.
* Reduces bottleneck.

---

### Disadvantages

* Complex control logic.
* Higher hardware cost.

---

### Conclusion

Multiple bus organization improves system performance significantly compared to single bus system.

---

## **5. Stack Organization in Processor**

Stack is a memory structure based on **Last In First Out (LIFO)** principle.

![Image](https://files.codingninjas.in/article_images/custom-upload-1715176392-b3dadcc5.webp)

![Image](https://homework.study.com/cimages/multimages/16/stack_push_operation2294814496370743228.jpg)

![Image](https://prepbytes-misc-images.s3.ap-south-1.amazonaws.com/assets/1673850739773-Stack%20Pointer3.png)

![Image](https://prepbytes-misc-images.s3.ap-south-1.amazonaws.com/assets/1673850739773-Stack%20Pointer1.png)

---

### Stack Operations

1. **PUSH** – Insert item into stack.
2. **POP** – Remove top item from stack.

---

### Stack Pointer (SP)

* Special register that holds address of top of stack.
* Automatically increments/decrements during PUSH/POP.

---

### Uses of Stack

* Subroutine calls
* Parameter passing
* Expression evaluation
* Interrupt handling

---

### Register Stack

When stack is implemented using registers instead of memory, it is called register stack.

Features:

* Faster access
* Limited size
* Used in high-speed processors

---

### Conclusion

Stack organization simplifies instruction format and supports efficient function calls.

---

## **6. Addressing Modes (Explain in Detail)**

### Definition

Addressing mode specifies how operand is located for execution of instruction.

Effective Address (EA) is the actual address used to fetch operand.

---

### 1. Immediate Addressing

Operand is directly present in instruction.
Example: `ADD R1, #5`

Advantages:

* Fast execution
* No memory access required

Limitation:

* Limited data size

---

### 2. Direct Addressing

Address field contains actual memory location.
EA = Address

Requires one memory reference.

---

### 3. Indirect Addressing

Address field contains address of another memory location.
EA = M[Address]

Requires two memory accesses.

---

### 4. Register Addressing

Operand is stored in register.
Very fast access.

---

### 5. Register Indirect Addressing

Register contains memory address.
EA = (Register content)

---

### 6. Indexed Addressing

EA = Address field + Index Register

Used in arrays and loops.

---

### 7. Base Register Addressing

EA = Base Register + Displacement

Used in memory relocation.

---

### 8. Relative Addressing

EA = PC + Address

Used in branch instructions.

---

### Conclusion

Addressing modes provide flexibility, reduce instruction size, and improve program efficiency.

---


#  **UNIT II**
## **Short Answers**

## **1. Design a 4-bit Combinational Incremental Circuit using Four Full Adders**

A combinational incrementer circuit is used to increase a binary number by 1.
It can be designed using four full adders connected in cascade form.

### Concept

To increment a 4-bit number (A3 A2 A1 A0) by 1:
We add binary value **0001** to the given number.

So:
[
A + 0001
]

---

### Circuit Design

* Use **4 Full Adders (FA0, FA1, FA2, FA3)**.
* Each full adder adds:

  * One bit of register A
  * One bit of constant 0 (except LSB)
  * Carry from previous stage

Connections:

* For LSB (FA0):

  * Inputs: A0, 1, Cin = 0
* For other stages:

  * Inputs: Ai, 0, Carry from previous FA

Carry propagates from LSB to MSB.

---

### Operation

* FA0 adds A0 + 1
* Carry generated is passed to FA1
* This continues until MSB

Final output:
[
S3 S2 S1 S0 = A + 1
]

---

### Conclusion

* Requires 4 full adders
* Carry propagation determines final result
* It is a ripple carry incrementer

---

## **2. Register A = 10011101**

Given 8-bit number:
[
A = 10011101
]

---

### (i) Arithmetic Shift Right (ASR)

Arithmetic shift right:

* MSB (sign bit) remains unchanged
* All other bits shift right by one position
* LSB is discarded

Original:
[
1\ 0\ 0\ 1\ 1\ 1\ 0\ 1
]

After ASR:
[
1\ 1\ 0\ 0\ 1\ 1\ 1\ 0
]

Final Answer:
[
11001110
]

---

### (ii) Arithmetic Shift Left (ASL)

Arithmetic shift left:

* All bits shift left by one position
* LSB becomes 0
* MSB is discarded

Original:
[
10011101
]

After ASL:
[
00111010
]

---

### Overflow Check

Overflow occurs if:

* Sign bit changes after shift

Original MSB = 1
New MSB = 0

Sign changed → **Overflow occurs**

---

## **3. Memory Read and Write Operations**

Memory operations involve interaction between CPU and memory using buses.

---

### Memory Read Operation

Steps:

1. CPU places memory address in **MAR (Memory Address Register)**.
2. Address is sent to memory through address bus.
3. CPU activates **Read control signal**.
4. Memory places requested data into **MDR (Memory Data Register)**.
5. Data transferred to CPU via data bus.

Thus, data moves from memory to CPU.

---

### Memory Write Operation

Steps:

1. CPU places address in MAR.
2. Data to be written is placed in MDR.
3. Address sent via address bus.
4. CPU activates **Write control signal**.
5. Data from MDR is stored into specified memory location.

Thus, data moves from CPU to memory.

---

### Conclusion

* Address Bus → carries address
* Data Bus → carries data
* Control Bus → carries Read/Write signals

These operations form the basic memory access cycle.

---

## **4. Different Types of Multipliers**

Multipliers are digital circuits used to multiply binary numbers.

---

### 1. Serial Multiplier

* Multiplies one bit at a time.
* Uses shift and add technique.
* Slower but requires less hardware.

---

### 2. Parallel Multiplier

* Multiplies all bits simultaneously.
* Faster but requires more hardware.
* Example: Array multiplier.

---

### 3. Booth’s Multiplier

* Used for signed number multiplication.
* Reduces number of addition operations.
* Efficient for 2’s complement numbers.

---

### 4. Wallace Tree Multiplier

* Uses tree structure to reduce partial products.
* Very fast.
* Used in high-speed processors.

---

### 5. Modified Booth Multiplier

* Improves Booth’s algorithm.
* Reduces partial products further.

---

### Conclusion

Choice of multiplier depends on:

* Speed requirement
* Hardware cost
* Power consumption

---

## **Long Answers**

## **1. Numerical on Booth’s Algorithm**

Booth’s Algorithm is used for multiplication of signed 2’s complement numbers.
It reduces the number of addition operations by encoding the multiplier.

### Example

Multiply:
[
(+7) \times (-3)
]

Binary representation (4-bit signed):

[
+7 = 0111
-3 = 1101 \quad (2’s complement form)
]

Initialize:

* Multiplicand (M) = 0111
* Multiplier (Q) = 1101
* Accumulator (A) = 0000
* Q₋₁ = 0
* Number of bits = 4

---

### Step 1

Check (Q₀, Q₋₁)

If 10 → A = A – M
If 01 → A = A + M
If 00 or 11 → No operation

Perform arithmetic right shift after each step.

---

### Iteration Table

| Step | Q₀ Q₋₁ | Operation    | After Shift (A Q Q₋₁) |
| ---- | ------ | ------------ | --------------------- |
| 1    | 1 0    | A = A – M    | Shift                 |
| 2    | 0 1    | A = A + M    | Shift                 |
| 3    | 1 0    | A = A – M    | Shift                 |
| 4    | 1 1    | No operation | Shift                 |

After 4 cycles:

Final result (A Q) =
[
11101011
]

Decimal value = **-21**

---

### Conclusion

Booth’s algorithm efficiently handles signed multiplication and reduces arithmetic operations.

---

## **2. Numerical on Floating Point Numbers**

Floating point numbers are represented in IEEE 754 format.

Single precision format:

* 1 bit → Sign
* 8 bits → Exponent
* 23 bits → Mantissa

---

### Example

Convert (+13.25) into IEEE 754 single precision.

---

### Step 1: Convert to Binary

[
13 = 1101
0.25 = 0.01
]

So:
[
13.25 = 1101.01
]

---

### Step 2: Normalize

[
1.10101 \times 2^3
]

---

### Step 3: Sign Bit

Positive → S = 0

---

### Step 4: Exponent

Bias = 127

[
Exponent = 3 + 127 = 130
]

Binary of 130:
[
10000010
]

---

### Step 5: Mantissa

Remove leading 1:

[
10101000000000000000000
]

---

### Final IEEE Representation

[
0\ 10000010\ 10101000000000000000000
]

---

### Conclusion

Floating point format allows representation of very large and very small numbers efficiently.

---

## **3. 2-bit by 2-bit Array Multiplier**

A 2×2 array multiplier multiplies two 2-bit numbers.

Let:
[
A = A_1A_0
B = B_1B_0
]

Product:
[
P = P_3P_2P_1P_0
]

---

### Step 1: Generate Partial Products

[
A_0B_0 → P_0
]

[
A_1B_0, A_0B_1
]

[
A_1B_1
]

---

### Step 2: Use Half Adders

Structure:

* P₀ = A₀B₀
* P₁ = A₁B₀ + A₀B₁ (using Half Adder)
* P₂ = Carry + A₁B₁ (Half Adder)
* P₃ = Final Carry

---

### Working Example

Let:
[
A = 10 (2)
B = 11 (3)
]

Multiplication:
[
2 \times 3 = 6 (0110)
]

---

### Characteristics

* Uses AND gates for partial products
* Uses Half Adders for summation
* Simple and fast for small bit numbers

---

## **4. Flowchart for Divide Operation (Signed Magnitude Form)**

Division in signed magnitude form includes sign checking and magnitude division.

![Image](https://www.researchgate.net/publication/359995605/figure/fig1/AS%3A11431281096732188%401668237142274/Flowchart-for-signed-magnitude-comparison-The-sign-bit-of-two-numbers-are-compared.ppm)

![Image](https://www.researchgate.net/publication/250612202/figure/fig3/AS%3A667661163847693%401536194234990/Flow-chart-of-Restoring-Division-Algorithm.ppm)

![Image](https://res.cloudinary.com/witspry/image/upload/witscad/public/content/courses/computer-architecture/restoring-division-algorithm-flowchart.png)

![Image](https://res.cloudinary.com/witspry/image/upload/witscad/public/content/courses/computer-architecture/flowchart-for-the-non-restoring-division.png)

---

### Steps of Algorithm

1. Start
2. Check sign of dividend and divisor
3. Determine sign of result (XOR of signs)
4. Convert both numbers to positive magnitude
5. Initialize remainder = 0
6. Repeat for n bits:

   * Shift left remainder and dividend
   * Subtract divisor
   * If remainder < 0 → restore and set quotient bit = 0
   * Else set quotient bit = 1
7. Assign sign to quotient
8. Stop

---

### Conclusion

Signed magnitude division separates sign processing from magnitude computation.

---

## **5. Look Ahead Carry Adder (LAC) – Derivation**

Ripple Carry Adder is slow due to carry propagation delay.

Look Ahead Carry Adder reduces delay by computing carry in advance.

---

### Step 1: Define Generate and Propagate

For each bit i:

[
G_i = A_i B_i
]

[
P_i = A_i + B_i
]

---

### Step 2: Carry Equation

[
C_{i+1} = G_i + P_i C_i
]

---

### For 4-bit Adder

[
C_1 = G_0 + P_0C_0
]

[
C_2 = G_1 + P_1G_0 + P_1P_0C_0
]

[
C_3 = G_2 + P_2G_1 + P_2P_1G_0 + P_2P_1P_0C_0
]

[
C_4 = G_3 + P_3G_2 + P_3P_2G_1 + P_3P_2P_1G_0 + P_3P_2P_1P_0C_0
]

---

### Block Diagram

![Image](https://vlabs.iitkgp.ac.in/coa/images/carrylookahead.png)

![Image](https://nandland.com/vhdl/modules/images/carry-lookahead-adder-4-bit.png)

![Image](https://i.sstatic.net/jfD9N.jpg)

---

### Advantages

* Faster than ripple carry adder
* Parallel carry computation

### Disadvantages

* Complex hardware
* More gates required

---

### Conclusion

Look Ahead Carry Adder significantly reduces carry propagation delay, improving speed of arithmetic operations.

---



#  **UNIT III**
## **Short Answers**

## **1. How does the Control Unit of a Computer Work?**

The Control Unit (CU) is a component of the CPU that directs and coordinates all operations of the computer system. It does not perform arithmetic operations itself; instead, it manages and controls data flow between the processor, memory, and input/output devices.

The working of the Control Unit follows the **instruction cycle**, which consists of fetch, decode, and execute phases.

1. **Fetch Phase** –
   The Control Unit fetches the instruction from memory.
   The Program Counter (PC) holds the address of the next instruction.
   The address is transferred to the Memory Address Register (MAR).
   The instruction is fetched into the Instruction Register (IR).

2. **Decode Phase** –
   The CU decodes the instruction to determine:

   * Operation to be performed
   * Addressing mode used
   * Source and destination operands

3. **Execute Phase** –
   The CU generates control signals to:

   * Activate ALU
   * Transfer data between registers
   * Initiate memory read/write

The CU generates timing and control signals such as:

* Read
* Write
* Increment PC
* Enable register transfer

Types of Control Unit:

* Hardwired Control Unit
* Microprogrammed Control Unit

Thus, the Control Unit acts as the supervisory component that ensures proper execution of instructions in correct sequence.

---

## **2. Differentiate between RISC and CISC**

RISC (Reduced Instruction Set Computer) and CISC (Complex Instruction Set Computer) are two types of processor architectures.

### 1. Instruction Set

* **RISC**: Uses small and simple instruction set.
* **CISC**: Uses large and complex instruction set.

### 2. Instruction Length

* **RISC**: Fixed length instructions.
* **CISC**: Variable length instructions.

### 3. Execution Time

* **RISC**: Most instructions execute in one clock cycle.
* **CISC**: Some instructions take multiple clock cycles.

### 4. Memory Access

* **RISC**: Load/Store architecture (only load and store access memory).
* **CISC**: Instructions can directly operate on memory.

### 5. Hardware Complexity

* **RISC**: Simple hardware design.
* **CISC**: Complex hardware design.

### 6. Example

* **RISC**: ARM, MIPS
* **CISC**: x86

Conclusion:
RISC focuses on speed and simplicity, while CISC focuses on reducing program size by providing complex instructions.

---

## **3. Differentiate between Horizontal and Vertical Microprogramming**

Microprogramming is a technique used in microprogrammed control units.

### Horizontal Microprogramming

* Control word is wide (many bits).
* Each bit directly controls a hardware signal.
* No need for decoding.
* Faster execution.
* Requires large memory.
* High parallelism possible.

Example:
One control word may activate multiple micro-operations simultaneously.

---

### Vertical Microprogramming

* Control word is narrow (fewer bits).
* Requires decoding before execution.
* Slower compared to horizontal.
* Requires less memory.
* Less parallelism.

---

### Comparison Table

| Feature            | Horizontal   | Vertical |
| ------------------ | ------------ | -------- |
| Control Word       | Wide         | Narrow   |
| Speed              | Fast         | Slower   |
| Memory Requirement | High         | Low      |
| Decoding           | Not required | Required |

Conclusion:
Horizontal microprogramming gives high speed but requires more hardware, while vertical microprogramming is compact but slower.

---

## **4. Different Types of Instruction Formats**

Instruction format refers to the arrangement of bits in an instruction.

It specifies:

* Opcode
* Operand(s)
* Addressing mode

---

### 1. Three-Address Instruction Format

Format:

```
OPCODE A B C
```

Example:

```
ADD R1, R2, R3
```

Meaning:
[
R1 = R2 + R3
]

Advantages:

* Fewer instructions required.
* Clear operand specification.

---

### 2. Two-Address Instruction Format

Format:

```
OPCODE A B
```

Example:

```
ADD R1, R2
```

Meaning:
[
R1 = R1 + R2
]

---

### 3. One-Address Instruction Format

Uses accumulator.

Example:

```
ADD X
```

Meaning:
[
AC = AC + X
]

---

### 4. Zero-Address Instruction Format

Used in stack organization.

Example:

```
ADD
```

Operands taken from stack automatically.

---

Conclusion:
Instruction format design affects instruction length, execution speed, and hardware complexity.

---


## **Long Answers**

## **1. Address Selection for Control Memory (With Neat Diagram)**

In a microprogrammed control unit, control signals are generated from microinstructions stored in **control memory**. The mechanism that selects the next microinstruction address is called **address selection for control memory**.

Control memory contains microinstructions arranged sequentially. The address of the current microinstruction is stored in the **Control Address Register (CAR)**.

### Main Components:

* Control Address Register (CAR)
* Control Memory
* Microinstruction Register (MIR)
* Address Sequencing Logic
* Mapping Logic
* Condition Flags

---

### Working Procedure:

1. Initially, CAR is loaded with the starting address.
2. CAR sends address to control memory.
3. Corresponding microinstruction is fetched into MIR.
4. Microinstruction contains:

   * Control field (control signals)
   * Next address field
   * Branch condition bits
5. Address Sequencer decides next address based on:

   * Incremented CAR (CAR + 1)
   * Branch address
   * Opcode mapping
   * External conditions (Zero, Carry, etc.)

---

### Neat Diagram:

```
        +----------------------+
        |     Control Memory   |
        +----------------------+
                  ^
                  |
        +----------------------+
        |  Control Address Reg |
        +----------------------+
                  |
        +----------------------+
        | Address Sequencer    |
        +----------------------+
          ^          ^         ^
          |          |         |
   Mapping Logic  Condition   CAR+1
                    Flags
```

---

### Conclusion

Address selection mechanism allows sequential execution, conditional branching, and opcode-based control transfer in microprogrammed control units.

---

## **2. Concept of Pipelining and Types of Pipelining**

Pipelining is a technique used to increase instruction throughput by overlapping execution phases of multiple instructions.

Instead of executing one instruction completely before starting the next, execution is divided into stages and processed simultaneously.

---

### Basic 5-Stage Instruction Pipeline:

1. Instruction Fetch (IF)
2. Instruction Decode (ID)
3. Execute (EX)
4. Memory Access (MEM)
5. Write Back (WB)

---

### Working Example:

| Clock | I1  | I2  | I3 |
| ----- | --- | --- | -- |
| 1     | IF  |     |    |
| 2     | ID  | IF  |    |
| 3     | EX  | ID  | IF |
| 4     | MEM | EX  | ID |
| 5     | WB  | MEM | EX |

Thus, multiple instructions execute in parallel.

---

### Types of Pipelining:

### 1. Instruction Pipeline

Overlaps instruction execution stages.

### 2. Arithmetic Pipeline

Used in floating-point operations where stages perform partial arithmetic tasks.

### 3. Processor Pipeline

Multiple processors perform different pipeline stages.

---

### Pipeline Hazards:

* Structural Hazard
* Data Hazard
* Control Hazard

---

### Advantages:

* Increases throughput
* Better CPU utilization

### Disadvantages:

* Complex design
* Hazard management required

---

## **3. Numerical on Stack Organized Computer**

In stack organized computer, operands are stored in stack and instructions use zero-address format.

Operations:

* PUSH
* POP

---

### Example:

Evaluate the expression:
[
(5 + 3) \times 2
]

Stack operations:

1. PUSH 5
2. PUSH 3
3. ADD
4. PUSH 2
5. MUL

---

### Stack Execution Table:

| Operation | Stack Content |
| --------- | ------------- |
| PUSH 5    | 5             |
| PUSH 3    | 5, 3          |
| ADD       | 8             |
| PUSH 2    | 8, 2          |
| MUL       | 16            |

Final Result = 16

---

### Explanation:

* ADD pops top two elements (5 and 3), pushes 8
* MUL pops 8 and 2, pushes 16

---

### Conclusion

Stack computers use zero-address instructions, reducing instruction size and simplifying hardware design.

---

## **4. Differences Between Hardwired and Microprogrammed Control Unit**

Control unit generates control signals required for instruction execution.

Two types exist:

---

### Hardwired Control Unit

* Control signals generated by combinational logic circuits.
* Uses decoders, encoders, flip-flops.
* Very fast operation.
* Difficult to modify.
* Used in RISC processors.
* Design is complex for large instruction sets.

---

### Microprogrammed Control Unit

* Control signals generated by microinstructions stored in control memory.
* Uses control memory and microinstruction sequencing.
* Slower than hardwired.
* Easy to modify or update.
* Used in CISC processors.
* Flexible design.

---

### Comparison Table:

| Feature      | Hardwired CU | Microprogrammed CU |
| ------------ | ------------ | ------------------ |
| Speed        | Fast         | Slower             |
| Flexibility  | Low          | High               |
| Design       | Complex      | Simple             |
| Modification | Difficult    | Easy               |
| Cost         | Lower        | Higher             |

---

### Conclusion

Hardwired control units provide high speed but low flexibility, whereas microprogrammed control units provide flexibility at the cost of speed.

---



#  **UNIT IV**
## **Short Answers**
# ✅ UNIT–4 : Memory Organization

---

## **1. What is Associative Memory? What are its Advantages and Disadvantages?**

Associative Memory is also called **Content Addressable Memory (CAM)**.
In this type of memory, data is accessed based on its content rather than its address.

In conventional memory, the CPU provides an address to access data.
But in associative memory, the CPU provides a data pattern, and the memory searches all stored words simultaneously.

Each memory word is compared in parallel with the input data using comparison logic.
If a match is found, a match signal is generated.

It is mainly used in:

* Cache memory (for tag comparison)
* Translation Lookaside Buffer (TLB)
* High-speed searching applications

---

### Advantages:

* Very fast searching (parallel comparison)
* Efficient for lookup tables
* Reduces search time complexity

### Disadvantages:

* Expensive hardware
* Complex circuitry
* Higher power consumption
* Limited storage capacity

---

### Conclusion:

Associative memory provides high-speed search capability but at high cost and complexity.

---

## **2. Differentiate between Static RAM and Dynamic RAM**

RAM is volatile memory used for temporary storage.

### Static RAM (SRAM)

* Stores data using flip-flops.
* Does not require refreshing.
* Faster access time.
* More expensive.
* Lower density (less storage per chip).
* Used in cache memory.

---

### Dynamic RAM (DRAM)

* Stores data using capacitors.
* Requires periodic refreshing.
* Slower than SRAM.
* Cheaper.
* Higher density (more storage per chip).
* Used in main memory.

---

### Comparison Table:

| Feature | SRAM         | DRAM        |
| ------- | ------------ | ----------- |
| Speed   | Fast         | Slower      |
| Refresh | Not required | Required    |
| Cost    | High         | Low         |
| Density | Low          | High        |
| Usage   | Cache        | Main memory |

---

### Conclusion:

SRAM is fast but costly, while DRAM is slower but economical and suitable for large memory.

---

## **3. Define HIT and MISS Ratio in Memory with Example**

In cache memory system, when CPU requests data:

* If data is found in cache → **Cache Hit**
* If data is not found in cache → **Cache Miss**

---

### Hit Ratio

Hit Ratio is the fraction of memory accesses found in cache.

[
\text{Hit Ratio} = \frac{\text{Number of Hits}}{\text{Total Memory Accesses}}
]

---

### Miss Ratio

Miss Ratio is the fraction of accesses not found in cache.

[
\text{Miss Ratio} = 1 - \text{Hit Ratio}
]

---

### Example:

If total memory accesses = 100
Hits = 80

Hit Ratio = 80/100 = 0.8 (80%)
Miss Ratio = 20/100 = 0.2 (20%)

---

### Conclusion:

Higher hit ratio improves system performance because cache access is much faster than main memory.

---

## **4. Define Virtual Memory**

Virtual Memory is a memory management technique that allows execution of programs larger than physical memory.

It creates an illusion of a very large memory for the user.

In virtual memory:

* Only required pages are loaded into RAM.
* Remaining pages stay in secondary storage (disk).

It uses:

* Paging
* Segmentation
* Page tables

When a required page is not in memory, a **page fault** occurs.

Advantages:

* Efficient memory utilization
* Supports large programs
* Provides memory protection

Disadvantages:

* Slower if too many page faults occur
* Requires complex hardware support

Conclusion:
Virtual memory improves flexibility and memory utilization in modern systems.

---

## **5. Define 2½D Memory Organization**

2½D memory organization is a technique used to increase memory capacity without increasing decoder complexity significantly.

In this organization:

* Memory is divided into multiple 2D memory arrays.
* An additional dimension (bank selection) is introduced.

Instead of one large memory array:

* Memory is arranged in smaller blocks (banks).
* Row and column decoding is done within each bank.
* Bank selection line selects specific memory block.

This reduces:

* Decoder size
* Hardware complexity

Advantages:

* Efficient memory expansion
* Reduced wiring complexity
* Better performance than simple 2D memory

Conclusion:
2½D memory organization is a practical compromise between 2D and fully 3D memory organization.

---


## **Long Answers**

## **1. Classification of Memory Based on Method of Access & Magnetic Disk**

### (A) Classification of Memory Based on Method of Access

Memory can be classified based on how data is accessed:

### 1. Sequential Access Memory (SAM)

* Data accessed in sequence.
* Access time depends on position.
* Example: Magnetic Tape.
* Slow but economical.

### 2. Direct Access Memory (DAM)

* Data accessed directly but not instantaneously.
* Requires mechanical movement.
* Example: Magnetic Disk.

### 3. Random Access Memory (RAM)

* Any location accessed directly with equal time.
* Example: Main memory (SRAM, DRAM).
* Fast access.

### 4. Associative Access Memory

* Access based on content.
* Example: Cache tag memory.

---

### (B) Construction of Magnetic Disk

Magnetic disk consists of:

* Circular platters coated with magnetic material
* Spindle for rotation
* Read/Write head
* Tracks (concentric circles)
* Sectors (division of track)
* Cylinders (same track across platters)

---

### Working of Magnetic Disk

* Disk rotates at high speed.
* Read/write head moves radially.
* Data stored magnetically on tracks.
* When required track comes under head, data is read/written.

---

### Components of Disk Access Time

1. **Seek Time** – Time to move head to correct track.
2. **Rotational Latency** – Time for sector to rotate under head.
3. **Transfer Time** – Time to transfer data.
4. **Controller Overhead** – Processing delay.

Total Access Time:

[
Access\ Time = Seek + Rotational\ Latency + Transfer\ Time
]

---

## **2. Numerical on Cache Memory**

Given:

* Cache Hit Time = 10 ns
* Main Memory Time = 100 ns
* Hit Ratio = 0.9

Find Average Memory Access Time (AMAT).

Formula:

[
AMAT = Hit\ Time + Miss\ Ratio \times Miss\ Penalty
]

Miss Ratio = 1 – Hit Ratio = 0.1

Miss Penalty = Main Memory Time = 100 ns

So:

[
AMAT = 10 + (0.1 \times 100)
]

[
AMAT = 10 + 10 = 20\ ns
]

---

### Interpretation

If there were no cache, access time would be 100 ns.
With cache, effective access time becomes 20 ns.

Thus, higher hit ratio significantly improves performance.

---

## **3. Mapping Virtual Address into Physical Address & Cache Writing Methods**

### Virtual to Physical Address Mapping

Virtual memory uses address translation.

Steps:

1. CPU generates Virtual Address.
2. Address divided into:

   * Page Number
   * Offset
3. Page number used to access Page Table.
4. Page table provides Frame Number.
5. Physical Address = Frame Number + Offset.

If page not in memory → Page Fault occurs.

Translation Lookaside Buffer (TLB) speeds up translation.

---

### Methods of Writing into Cache

### 1. Write Through

* Data written to both cache and main memory.
* Ensures consistency.
* Slower due to frequent memory writes.

### 2. Write Back (Copy Back)

* Data written only in cache.
* Main memory updated when block replaced.
* Faster but complex.

### 3. Write Allocate

* On write miss, block loaded into cache first.

### 4. No Write Allocate

* On write miss, data written directly to memory.

---

## **4. Memory Hierarchy (Speed, Size and Cost)**

Memory hierarchy arranges storage devices based on speed, size, and cost.

```
Registers
Cache
Main Memory
Secondary Memory
Secondary Storage
```

---

### Characteristics:

| Level       | Speed     | Size       | Cost per Bit |
| ----------- | --------- | ---------- | ------------ |
| Registers   | Very High | Very Small | Very High    |
| Cache       | High      | Small      | High         |
| Main Memory | Medium    | Large      | Moderate     |
| Disk        | Low       | Very Large | Low          |

---

### Explanation:

* Higher level → Faster, smaller, expensive
* Lower level → Slower, larger, cheaper

Purpose:

* Balance cost and performance
* Provide illusion of large, fast memory

---

## **5. Short Notes**

---

### (A) Magnetic Disk

Magnetic disk is a secondary storage device.
Data stored magnetically on rotating platters.

Features:

* Direct access storage
* Organized into tracks and sectors
* Used in Hard Disk Drives (HDD)

Advantages:

* Large storage capacity
* Rewritable

Disadvantages:

* Mechanical delay
* Slower than SSD

---

### (B) Magnetic Tape

Magnetic tape is sequential access storage device.

Features:

* Plastic ribbon coated with magnetic material
* Data stored sequentially
* Used for backup and archival

Advantages:

* Low cost
* Large storage

Disadvantages:

* Slow access
* Not suitable for frequent updates

---

### (C) Optical Disk

Optical disk stores data using laser technology.

Examples:

* CD
* DVD
* Blu-ray

Features:

* Data stored as pits and lands
* Read using laser beam

Advantages:

* Portable
* Durable

Disadvantages:

* Limited rewrite capability
* Slower than hard disk

---


#  **UNIT V**
## **Short Answers**

## **1. Difference between Synchronous and Asynchronous Serial Modes of Data Transfer**

Serial data transfer means data is transmitted one bit at a time over a communication line. It can be done in two modes: synchronous and asynchronous.

### Synchronous Serial Transmission

In synchronous mode, data transfer is controlled by a common clock signal shared between sender and receiver. Both devices operate at the same clock frequency.

* Data is sent in blocks or frames.
* No start and stop bits are required for each character.
* High data transfer speed.
* Efficient for large data transfer.
* Requires precise clock synchronization.
* Used in high-speed communication systems.

---

### Asynchronous Serial Transmission

In asynchronous mode, no common clock is shared. Each character is transmitted independently.

* Each character contains start and stop bits.
* Start bit indicates beginning of transmission.
* Stop bit indicates end of transmission.
* Slower due to extra bits.
* Simpler and cheaper implementation.
* Used in low-speed communication (e.g., UART).

---

### Key Differences

| Feature    | Synchronous           | Asynchronous           |
| ---------- | --------------------- | ---------------------- |
| Clock      | Common clock required | No common clock        |
| Speed      | High                  | Low                    |
| Efficiency | More efficient        | Less efficient         |
| Overhead   | Less                  | More (start/stop bits) |

Conclusion:
Synchronous transmission is faster and more efficient, while asynchronous transmission is simpler and suitable for low-speed communication.

---

## **2. Functions Performed by an Input/Output Unit**

The Input/Output (I/O) unit acts as an interface between computer system and external devices.

### Main Functions:

1. **Data Transfer**
   Transfers data between CPU/memory and external devices.

2. **Device Communication**
   Provides communication path between internal system and peripherals.

3. **Data Conversion**
   Converts data from device format to binary format and vice versa.

4. **Buffering**
   Stores temporary data to match speed difference between CPU and I/O devices.

5. **Error Detection**
   Detects and reports transmission errors.

6. **Control and Timing**
   Generates control signals for read/write operations.

7. **Interrupt Handling**
   Sends interrupt signals to CPU when I/O operation is complete.

8. **Address Recognition**
   Recognizes its own address when CPU issues command.

Conclusion:
The I/O unit ensures smooth and efficient communication between the computer system and external devices.

---

## **3. Why DMA Gets Priority over CPU in Memory Transfer?**

DMA (Direct Memory Access) is a technique that allows I/O devices to transfer data directly to or from memory without CPU intervention.

When both CPU and DMA request memory access, DMA is usually given higher priority.

### Reasons:

1. **High-Speed Data Transfer**
   I/O devices like disk require fast data transfer to avoid data loss.

2. **Bulk Data Movement**
   DMA handles large blocks of data efficiently.

3. **Reduces CPU Load**
   CPU is free to perform other tasks.

4. **Prevents Buffer Overflow**
   Delay in DMA servicing may cause buffer overflow in devices.

5. **Real-Time Requirements**
   Some devices need immediate memory access.

---

### Working Principle

* DMA sends request to CPU.
* CPU grants bus control.
* DMA transfers data directly between memory and device.
* After completion, control returns to CPU.

Conclusion:
DMA gets priority because it ensures efficient and uninterrupted high-speed data transfer, improving overall system performance.

---


## **Long Answers**

## **1. Destination–Initiated Transfer using Handshaking Method**

In asynchronous data transfer, sender and receiver do not share a common clock. Therefore, handshaking signals are used to coordinate data transfer. In destination-initiated transfer, the receiver (destination) starts the communication.

### Concept:

In this method, the destination device sends a request signal to the source when it is ready to receive data. This ensures proper synchronization.

---

### Steps of Operation:

1. Initially, destination device checks if it is ready.
2. It sends a **Data Request (DR)** signal to the source.
3. Source places data on the data bus.
4. Source activates **Data Valid (DV)** signal.
5. Destination reads the data.
6. Destination sends **Acknowledge (ACK)** signal.
7. Source removes data and resets DV.
8. Destination resets request line.

---

### Characteristics:

* No common clock required.
* Reliable for devices of different speeds.
* Prevents data loss.
* Slightly slower due to control signal overhead.

---

### Diagram:

```
Destination ---- DR ----> Source
Source ------ Data ----> Destination
Source ---- DV ----> Destination
Destination --- ACK ---> Source
```

---

### Conclusion:

Destination-initiated handshaking ensures safe and synchronized transfer when receiver controls timing.

---

## **2. Define Interrupt and Types of Interrupt**

### Definition:

An interrupt is a signal generated by hardware or software that temporarily halts the current CPU execution and transfers control to an Interrupt Service Routine (ISR).

After servicing, CPU resumes previous program.

---

### Types of Interrupt:

### 1. Hardware Interrupt

Generated by external devices (keyboard, disk, I/O).
Example: I/O completion interrupt.

---

### 2. Software Interrupt

Generated by program instruction.
Example: System call.

---

### 3. Maskable Interrupt

Can be disabled by CPU using interrupt mask.

---

### 4. Non-Maskable Interrupt (NMI)

Cannot be disabled. Used for critical events.

---

### 5. Vectored Interrupt

ISR address is predefined.

---

### 6. Non-Vectored Interrupt

ISR address must be supplied externally.

---

### Interrupt Handling Steps:

1. Save current PC
2. Load ISR address
3. Execute ISR
4. Restore PC
5. Resume program

---

### Conclusion:

Interrupt mechanism improves CPU efficiency by handling events only when required.

---

## **3. Differences Between Interrupt Initiated I/O and Programmed I/O**

Both are methods for data transfer between CPU and I/O devices.

---

### Programmed I/O:

* CPU continuously checks device status (polling).
* CPU waits until device becomes ready.
* CPU directly transfers data.
* Wastes CPU time.
* Simple to implement.
* Suitable for small data transfers.

---

### Interrupt Initiated I/O:

* Device sends interrupt when ready.
* CPU performs other tasks meanwhile.
* CPU services device only when interrupt occurs.
* Better CPU utilization.
* Requires interrupt hardware.
* More efficient than polling.

---

### Comparison Table:

| Feature         | Programmed I/O | Interrupt I/O       |
| --------------- | -------------- | ------------------- |
| CPU Involvement | Continuous     | Only when interrupt |
| Efficiency      | Low            | High                |
| Hardware        | Simple         | More complex        |
| CPU Idle Time   | High           | Low                 |

---

### Conclusion:

Interrupt I/O is superior to programmed I/O because it reduces CPU idle waiting and improves performance.

---

## **4. Modes of Data Transfer and Detailed Explanation of DMA**

### Modes of Data Transfer:

### 1. Programmed I/O

CPU polls device and transfers data.

### 2. Interrupt Initiated I/O

Device interrupts CPU when ready.

### 3. Direct Memory Access (DMA)

Data transferred directly between I/O device and memory without CPU intervention.

---

## Direct Memory Access (DMA)

DMA allows high-speed data transfer directly to memory.

### DMA Components:

* DMA Controller
* Address Register
* Word Count Register
* Control Register

---

### Working Steps:

1. CPU initializes DMA controller with:

   * Starting memory address
   * Number of words
   * Direction of transfer
2. DMA requests bus control.
3. CPU grants bus (Bus Grant).
4. DMA transfers data directly between device and memory.
5. After completion, DMA interrupts CPU.

---

### DMA Transfer Modes:

* Burst Mode
* Cycle Stealing Mode
* Transparent Mode

---

### Why DMA is Superior:

1. Reduces CPU workload.
2. High-speed block transfer.
3. Efficient for large data movement.
4. Prevents CPU bottleneck.
5. Better overall system performance.

---

### Comparison Summary:

| Mode       | CPU Usage | Speed    |
| ---------- | --------- | -------- |
| Programmed | High      | Slow     |
| Interrupt  | Medium    | Moderate |
| DMA        | Low       | Fast     |

---

### Conclusion:

DMA is the most efficient mode for large and high-speed data transfer as it allows direct memory access without CPU intervention.

---
