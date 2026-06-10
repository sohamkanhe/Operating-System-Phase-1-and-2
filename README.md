# Multi-Programming Operating System (MOS) Simulation

This project is a simulation of a Multi-Programming Operating System (MOS) implemented in C++. It is divided into two phases, each increasing in complexity and functionality.

## Project Structure

- `os_phase1.cpp`: Implementation of Phase 1 of the MOS simulation.
- `os_phase2.cpp`: Implementation of Phase 2 of the MOS simulation, introducing paging and advanced error handling.
- `input.txt`: Input file containing control cards, user programs, and data.

## Phase 1: Basic MOS Simulation

Phase 1 implements a basic version of the MOS with a simple instruction set and direct memory access.

### Features
- **Memory:** 100 rows by 4 columns (400 bytes).
- **Registers:** Instruction Register (IR), General Purpose Register (R), Instruction Counter (IC).
- **Control Cards:**
  - `$AMJ`: Start of a job.
  - `$DTA`: Start of data.
  - `$END`: End of a job.
- **Instruction Set:**
  - `GD`: Get Data (Read from input to memory).
  - `PD`: Put Data (Write from memory to output).
  - `H`: Halt (Terminate program).
  - `LR`: Load Register.
  - `SR`: Store Register.
  - `CR`: Compare Register.
  - `BT`: Branch on True.

### Execution
1. Ensure `input.txt` is present in the directory.
2. Compile: `g++ os_phase1.cpp -o os_phase1`
3. Run: `./os_phase1`
4. Output will be generated in `output.txt`.

---

## Phase 2: Advanced MOS Simulation with Paging

Phase 2 builds upon Phase 1 by introducing a paging system for memory management and a robust error-handling mechanism.

### Features
- **Paging System:** Implements Virtual-to-Physical address translation using a Page Table.
- **Memory Allocation:** Uses randomized block allocation for physical memory pages.
- **Physical Memory:** 300 blocks, each containing 4 bytes.
- **Error Handling:** Detects and reports various termination conditions:
  - **Time Limit Exceeded (TTE):** Program execution exceeds specified time.
  - **Line Limit Exceeded (LLE):** Program exceeds the specified number of output lines.
  - **Opcode Error:** Invalid instruction opcode.
  - **Operand Error:** Invalid memory operand.
  - **Invalid Page Fault:** Accessing unallocated or invalid pages.
  - **Out of Data:** Program requests data but none is left in the input.

### Execution
1. Ensure `input.txt` is present in the directory.
2. Compile: `g++ os_phase2.cpp -o os_phase2`
3. Run: `./os_phase2`
4. Output will be generated in `output1.txt`.

## Input File Format (`input.txt`)

The input file follows a specific format for the simulation to process jobs correctly:

```text
$AMJ[JobID][TimeLimit][LineLimit]
[User Program Instructions]
$DTA
[Data Lines]
$END[JobID]
```

## Requirements

- C++ Compiler (e.g., GCC/G++)
- Standard C library headers (`stdio.h`, `stdlib.h`, `string.h`, `time.h`, `stdint.h`)
