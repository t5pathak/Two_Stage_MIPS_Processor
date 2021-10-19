# Two Stage MIPS Instruction Set Architecture
We have implemented a two stage processor with MIPS ISA. We have several modules which comprised of the project. Starting with ALU, Control Unit and the Fetch Unit. We have implemented around 27 instructions (14 R-type, 11 I-type and 2 Jump instructions).

## Architectural Design
- Its a 2 stage architecture, which works on the FDE ( Fetch Decode and Execute ) principle
- **Decode Unit** : Takes the instruction pointed by the PC and hands over control to it.
- **Fetch Unit** : It points to the right instruction and and adds offset for the branch instruction.
- **Execute** : At the falling clock edge, it updates the value of the registers
- **ALU** which is implemented with a lot of blocks for arithmetic, logical and shifting operations.

## Main Memory Unit
- **Main Memory** : using a 2D array with dimensions of 32x32. Also the memory is word based ie. it is 4 byte in length. The memory design is Harvard based ie. there is a unique data and instruction memory. TOTAL SIZE USED = 1Kb
- **Instruction Memory** : is also a 2D array. The is size is 128x8. This memory is initialised in the fetch unit. TOTAL SIZE USED = 128 Bytes

## Instruction Supported

|Intruction Type |Instruction Supported|
|-----|--------|
|R-Type|ADD, AND, NOR, OR, SUB, XOR, SLT, SLTU, SLL, SLLV, SRA, SRAV, SRL, SRLV|
|I-Type|ADDI, ANDI , SLTI, ORI , XORI, BGTZ,BLEZ,BNE,LB,SB ,BEQ|
|J- Type|JUMP, JAL|

## Instruction not Supported

SLTIU, DIV ,MULT, PAUSE, PREF, PREFE, WAIT, TLT, TLBP

## Processor Clock Frequency
- The maximum clock frequency supported is 1.2GHz
- The minimum clock period is 0.833ns.

## Advantages and Disadvantages
Pros
1. Separate data memory and instruction memory
2. RTL makes it easy to visualise flow of MIPS processor 3. Pipeline frequency improves time efficiency

Cons
1. No Branch Delay Slot - Thus code needs a NO-OP instruction
2. All modules in single code make debugging difficult
3. Instructions need to fed in the binary format ( according to the format for
that instruction )

## Processor Layout
<p align="center">
    <img width="723" alt="Processor_layout" src="https://user-images.githubusercontent.com/44245211/137942454-33aa2aa4-1241-4056-965d-133f6083a621.png">
  </p>

## Directory Structure
- ```src``` folder contains the source code. 
- ```result``` contains the text file containing binary output 
 
## Running the code
Any changes which need to be made, must be made in the code block under the heading "Main" only
1. Run the code in Xylinx.
2. Observe the timing diagram to observe the output of the processor.
