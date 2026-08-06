CPU²: A Two-Dimensional CPU Memory Concept

The CPU described in this documentation utilizes a memory storage array that is two-dimensional, with a X and Y address component.  This alters how certain aspects of the CPU behave, such as how low-level computer instructions (“opcodes” or “microcodes”) are executed and how memory is accessed.

How this compares to conventional CPUs

Conventional CPUs use a single-dimensional memory array for program and data space.  Each memory location is assigned a unique numeric identifier known as a memory address.  Being single-dimensional, these memory addresses are a single numeric range.

On these conventional CPUs, the current execution point is called the "program counter", which is an index pointing at the current memory address of the instruction being executed.  Branching on these CPUs consists primarily of moving around the linear address space by directly or indirectly specifying partial or full memory addresses to jump to, or using triggered signals to jump to pre-defined addresses called interrupt vectors.

This "2D" CPU concept, however, utilizes a two-dimensional memory array (i.e. a memory map with an address space of 65536 locations is now represented as a 256x256 space).  The program counter on this CPU consists of a X and Y address and an execution direction (north/south/west/east or -Y/+Y/-X/+X).  On this "2D" CPU, the branch instructions have been designed for conditionally altering the execution direction based on flag states and doesn't have any conventional address-based branching or interrupt vectors available, other than a set of limited relative positional jump instructions.  

Also, because all of the addressing and branching on this CPU is relative, Most properly written programs can be rotated within the two-dimensional memory area and will continue to execute normally.

Note: This CPU concept is not intended for use as a general-purpose CPU technology -- it is specifically designed to operate as a programming game similar to the "Core War" game concept (created by D.G.Jones and A.K.Dewdney in 1984).  Certain aspects of its design are purposely configured to provide a more challenging environment for assembly programmers to spur more creativity in how programs are developed and optimized under this environment.  This CPU also has certain game-specific features that would not be relevant in a conventional CPU design.

My development intention of this CPU concept is that it be programmed in a hardware definition language to run natively on an FPGA chip rather than being programmed in software.

 Sunperp
