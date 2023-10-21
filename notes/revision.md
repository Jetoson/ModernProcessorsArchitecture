# Digital Logic

- **Logic Gates**
  - These are the building blocks used to implement Boolean algebra operations.
  - They are typically made up of transistors and, in some cases, resistors.

- **Logic Families**
  - These are groups of logic gates.
  - Examples include Wired Logic, RTL, DTL, TTL, ECL, NMOS, CMOS.

- **"Set-and-forget" Principle**
  - Silicon devices (like transistors) are constructed and then forgotten.
  - Logic gates are constructed using these transistors, and once done, we forget about the transistors.
  - Integrated circuits are built using these logic gates, and once constructed, we no longer focus on the individual logic gates.
  - Processors are built using these integrated circuits, and after that, the underlying electronics are abstracted away.
  - Processors are programmed in assembly language, and post that, the assembly code is abstracted away.

- **Combinational Logic Circuit**
  - This is a logic gate that applies a function based on its inputs.
  - Examples include multiplexers, adders, encoders and decoders, comparators, and ROM memory.

- **Sequential Logic Circuit**
  - The output depends on both the current input and the previous states of the circuit.
    - **Asynchronous (latch)**: Output changes in real-time.
    - **Synchronous (flip-flop)**: Output changes on the rising (or falling) edge of a clock signal.

# Verilog - A Hardware Description Language (HDL)

- **Purpose**
  - Used for the formal specification of digital electronic circuits.

- **Characteristics**
  - Contains abstractions or ways to generate logic gates through code.

- **FPGA**
  - This is a platform used for developing an integrated circuit from scratch.
  - Essentially, it's a matrix of logic gates.

- **Advantages of FPGA over a Processor**
  - Designs can be reconfigured rapidly.
  - High degree of parallelism.
  - Precise control over timing, such as switching the clock signal every 13ns.

- **Module**
  - The basic unit in Verilog language.
  - Consists of two main components: interface description and the circuit's behavior.
  - The provided code snippets show how to define, implement, and instantiate a module.

 ```Verilog
// module definition 
        module <module_name>(
            <type_of_port_1> <name_of_port_1>, 
            <type_of_port_2> <name_of_port_2>,
            ...
            <type_of_port_n> <name_of_port_n>
            ); 
        
        // module implementation.
        
        endmodule

        // module instantiation.
        // Not connecting all ports of a module is not an error!
        module_name <instance_name>(
            .name_of_port_1(<name_of_argument_1>), 
            .name_of_port_2(<name_of_argument_2>), 
            .name_of_port_3(<name_of_argument_3>), 
            ..., 
            .name_of_port_n(<name_of_argument_n>)
        );
```

- **Declarations**
  - **Wire**: Represents physical connections between components.
  - **Register (reg)**: Holds a value and can be assigned a value.

- **Structures**
  - **Continuous Assignments (assign)**: Used only on wire and indicates the output of a combination of logic gates.
  - **Initial blocks**: Define an initial state and are triggered only once.
  - **Always blocks**: Contain actions that are executed periodically.

- **Primitives**
  - Basic logical functions like and, or, nor, etc.
  - For built-in primitives, instance names are optional.
  - Output signals must be declared first, followed by input signals.
  - Users can define their own primitives through truth tables.

- **Development Environment**
  - **Xilinx ISE**: Used for code synthesis, simulation, and programming on boards.
  - A Verilog module is defined in a file named with the ".v" extension.
  - For module testing, a test module (test fixture) is used where input values are manually specified.
  - Several other features are also mentioned, including simulation time units and wait constructs.

# Verilog Module Description

- **Description Types**
  - **Structural level**: Describes the module's internal structure using primitives and other modules.
  - **Data flow level**: Describes the relationship between inputs and outputs using expressions.
  - **Procedural level**: Describes the module's functionality in an algorithmic manner.

- **Assignments**
  - Different types of assignments and their characteristics are detailed, including continuous assignments, blocking and non-blocking assignments.

- **Initial and Always Blocks**
  - Mark procedural sections of the module.
  - Instructions inside are executed in sequence.
  - Sensitivity lists define the triggers for the always block.

- **Control Constructs**
  - Various conditional and loop constructs are explained, along with synchronization and event-driven constructs.

# Finite State Machines (FSM)

- **Definition**
  - A finite automaton is a computational model used for designing software programs or sequential circuits.
  - At any given time, it can be in one of a finite number of possible states.
  - Transitions can be made between these states based on conditions.
  - FSMs can accept inputs and produce outputs.

- **Mealy Machines**: The output depends on both the current state and current input.

- **Moore Machines**: The output depends only on the current state.

- **FSM in Verilog**
  - Various steps like encoding states, specifying output behavior, sequential transition logic, and state-changing logic are discussed.

# Arithmetic Logic Unit (ALU)

- **Role**
  - It is a fundamental component of any processor.
  - Responsible for almost all numerical computations.

- **Capabilities**
  - Can be designed to execute any operation.
  - Complex operations come with increased costs and higher heat dissipation.
  - Ideally, an operation should be executed in just one clock cycle.

- **Status Register**
  - Each bit in this register signals a particular event or condition.

# Pipelining

- **Phases of Instruction Execution**
  - Phases like Instruction Fetch, Decode, Execute, Memory Access, and Register Write Back are discussed.

- **Instruction Execution**
  - Typically, instructions are executed sequentially.
  - In pipelining, at any given moment, each phase contains a different instruction, allowing for more efficient and parallel execution.

---
