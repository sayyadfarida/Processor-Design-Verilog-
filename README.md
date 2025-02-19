COMPANY: CODTECH IT SOLUTIONS

NAME: Farida Sayyad

INTERN ID: :CT6WJJR

*DOMAIN*: VLSI

DURATION: 6 WEEEKS

MENTOR: NEELA SANTOSH


This repository presents a complete Verilog implementation of a 4-stage pipelined processor that supports a minimal instruction set including ADD, SUB, and LOAD. The design is intended as an educational and experimental platform for those interested in understanding pipelined processor architectures in digital design and FPGA development. By breaking down the processor into four distinct stages—Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), and Write Back (WB)—this project demonstrates how multiple instructions can be processed concurrently to improve throughput and overall performance.

In the IF stage, the processor uses a program counter (PC) to index into a small instruction memory (a ROM) that stores 16-bit instructions. The instruction is then captured along with the current PC value in pipeline registers (IF/ID) to be used in subsequent stages. This stage is crucial for maintaining a steady stream of instructions, ensuring that the pipeline remains full.

During the ID stage, the fetched instruction is decoded. The instruction format has been designed to accommodate both R-type arithmetic instructions (ADD and SUB) and I-type memory instructions (LOAD). For arithmetic instructions, the opcode is followed by fields that specify the destination register and two source registers. For the load instruction, the opcode is accompanied by the destination register and a 9-bit immediate value representing the address in data memory. The register file, which contains eight 16-bit registers, is read during this stage to retrieve operand values for R-type instructions. All decoded information and read data are stored in the ID/EX pipeline registers.

The EX stage performs the core operations. For ADD and SUB instructions, the arithmetic logic unit (ALU) computes the sum or difference of the source register values. In the case of a LOAD instruction, the immediate value is used to access an internal data memory array, and the corresponding data is retrieved. The result of the operation is then stored along with the destination register identifier in the EX/WB pipeline registers. This stage exemplifies how pipelining allows multiple instructions to be processed in parallel, as each stage works on different instructions concurrently.

Finally, in the WB stage, the result produced in the EX stage is written back into the register file at the destination register specified by the instruction. This completes the instruction cycle and prepares the processor for the next set of operations. The use of synchronous operations and pipelined registers ensures that all stages are coordinated with the clock signal, minimizing hazards and enabling high-speed operation.

The repository is organized to facilitate easy integration, testing, and further extension. The code is well-commented and structured into logical sections representing each pipeline stage. The initial block in the top-level module initializes the instruction memory with a sample program that includes LOAD, ADD, and SUB instructions, and also populates the data memory and register file with default values. This self-contained design can be simulated using tools such as Icarus Verilog, ModelSim, or Vivado, offering a hands-on demonstration of pipelined processor behavior.

Output:
![Image](https://github.com/user-attachments/assets/50792047-987f-46a6-8cd8-f777358d669b)
