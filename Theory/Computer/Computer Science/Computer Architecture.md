Tags: [[CS Unclassified]]
### 1. **Fundamental Concepts**

#### **Architecture vs. Organization**

- **Architecture**: Refers to the abstract design and functional behavior of a computer system, including the instruction set and the overall structure.
- **Organization**: Refers to the physical implementation and the details of how architectural elements are connected and work together.

### 2. **Major Components of a Computer System**

#### **Central Processing Unit (CPU)**

- **Arithmetic Logic Unit (ALU)**: Performs arithmetic and logical operations.
- **Control Unit (CU)**: Directs the operation of the processor.
- **Registers**: Small, fast storage locations within the CPU.
- **Cache**: High-speed memory that stores frequently accessed data to speed up processing.

#### **Memory**

- **Primary Memory**:
    - **RAM (Random Access Memory)**: Volatile memory used to store data and instructions currently in use.
    - **ROM (Read-Only Memory)**: Non-volatile memory used to store firmware.
- **Secondary Memory**:
    - **Hard Disk Drives (HDDs)**: Magnetic storage devices for long-term data storage.
    - **Solid-State Drives (SSDs)**: Faster storage devices that use flash memory.

#### **Input/Output (I/O) Devices**

- **Input Devices**: Keyboards, mice, scanners, etc.
- **Output Devices**: Monitors, printers, speakers, etc.
- **I/O Controllers**: Manage the communication between the CPU and peripheral devices.

#### **Bus System**

- **Data Bus**: Transfers data between components.
- **Address Bus**: Carries addresses from the CPU to memory and I/O devices.
- **Control Bus**: Carries control signals to manage operations.

### 3. **Instruction Set Architecture (ISA)**

- Defines the set of instructions the CPU can execute.
- **Instruction Formats**: Specifies the structure of instructions.
- **Addressing Modes**: Defines how operands are specified.
- **Instruction Types**: Categories like arithmetic, logic, data transfer, and control instructions.

### 4. **Pipelining**

- Technique used to improve CPU performance by overlapping the execution of multiple instructions.
- **Stages**: Fetch, Decode, Execute, Memory Access, Write-Back.
- **Pipeline Hazards**:
    - **Data Hazards**: Occur when instructions depend on the results of previous instructions.
    - **Control Hazards**: Arise from branch instructions that alter the flow of execution.
    - **Structural Hazards**: Occur when hardware resources are insufficient to support all concurrent operations.

### 5. **Parallelism**

- **Instruction-Level Parallelism (ILP)**: Executes multiple instructions simultaneously within a single CPU core.
- **Thread-Level Parallelism (TLP)**: Multiple threads or processes run concurrently.
- **Data-Level Parallelism (DLP)**: Operations on multiple data points simultaneously, often through SIMD (Single Instruction, Multiple Data) instructions.

### 6. **Memory Hierarchy**

- **Registers**: Fastest but limited in size.
- **Cache**: Faster than RAM, smaller in size.
- **Main Memory (RAM)**: Larger, slower.
- **Secondary Storage**: Slowest, largest.

### 7. **Virtual Memory**

- Allows a computer to compensate for physical memory shortages by temporarily transferring data to disk storage.
- **Paging**: Divides memory into fixed-size pages.
- **Segmentation**: Divides memory into segments of varying sizes.

### 8. **Performance Metrics**

- **Clock Speed**: Frequency at which the CPU executes instructions.
- **MIPS (Million Instructions Per Second)**: Measure of the CPU's performance.
- **Throughput**: Amount of work done in a given time period.
- **Latency**: Time taken to execute a single task.

### 9. **Advanced Topics**

- **Superscalar Architecture**: Allows multiple instructions to be executed per clock cycle.
- **Out-of-Order Execution**: CPU can execute instructions as resources become available, not strictly in the order they appear.
- **Speculative Execution**: CPU guesses the path of branch instructions and executes instructions ahead of time.

### 10. **System Software Interaction**

- **Operating System (OS)**: Manages hardware resources and provides services to applications.
    - **Kernel**: Core part of the OS that manages low-level operations.
    - **System Calls**: Interfaces through which applications request services from the OS.

### 11. **Compilers and Languages**

- **Compilers**: Translate high-level source code into machine code.
    - **Lexical Analysis**: Converts source code into tokens.
    - **Syntax Analysis**: Parses tokens to create a syntax tree.
    - **Semantic Analysis**: Checks for semantic errors.
    - **Optimization**: Improves the efficiency of the code.
    - **Code Generation**: Produces machine code.
- **Programming Languages**:
    - **High-Level Languages**: Provide abstraction from hardware (e.g., Python, Java).
    - **Low-Level Languages**: Provide little abstraction from hardware, allowing for fine-grained control (e.g., Assembly).

### Hierarchical Summary

1. **Hardware**
    
    - CPU: ALU, CU, Registers, Cache
    - Memory: RAM, ROM, Secondary Storage
    - I/O Devices and Controllers
    - Bus System
2. **Instruction Set Architecture (ISA)**
    
    - Instruction Formats, Addressing Modes, Instruction Types
3. **Performance Enhancements**
    
    - Pipelining, Parallelism, Memory Hierarchy, Virtual Memory
4. **System Software**
    
    - Operating System: Kernel, System Calls
5. **Software Development**
    
    - Compilers: Phases, Optimization, Code Generation
    - Programming Languages: High-Level, Low-Level

### Example of Integrated Operations

1. **Program Execution**:
    
    - A program is written in a high-level language.
    - The compiler translates the program into machine code.
    - The OS loads the machine code into RAM.
    - The CPU fetches, decodes, and executes instructions using pipelining and parallelism.
    - Memory hierarchy ensures fast access to frequently used data.
    - Virtual memory manages larger datasets efficiently.
2. **System Start-Up**:
    
    - BIOS/UEFI initializes hardware and loads the bootloader.
    - The bootloader loads the OS kernel and HAL.
    - The OS initializes system services and hardware drivers.
    - User applications are loaded and executed.

[[Memory Allocation]]