# processor_practical
A CPU design in digital. It is based on RUN2223 CPU, a 32-bit CPU designed specifically for the course Processors. In the practical assignment for this course, our task was to create an implementation of the RUN2223 CPU in Digital, according to the specifications in the included manual.

## How to set up
To view the CPU design, you need to install the digital circuit design tool *Digital*. It is completely open-source and can be installed from the github page [here](https://github.com/hneemann/Digital).

To simulate the computer circuit (of which our CPU is a major component) in Digital:
 0. Start up digital, which you can do by running *Digital.sh* as a program in the installation folder of Digital.
 1. Open *Computer.dig*.
 2. Load one of the included (machine code) programs, such as *clear_screen.hex* or (recommended), by going to the navbar of Digital and selecting *Edit -> Circuit Specific Settings -> Advanced tab* and ticking the box *Preload program memory at startup*, and then selecting one of the *.hex* files included in the folder *tools-and-examples*.
 3. Click the *white* play button with *no* additional markings (the other two play buttons are for testing or single-step simulation) in the top bar of Digital. This should start the simulation.

To view subcomponents, you can simply open the other files, or select components and click "open circuit" in the component menu.

## What we did
Bram Weessies and I received:
 1. A manual which described, on a high level:
    - a specification of the input and output interfaces of the RUN2223 CPU, which enables it to communicate with the rest of the computer
    - a description of the instruction cycle of the CPU
    - a general overview of the architecture of the CPU, and how it is divided into subcomponents
    - a specification of the assembly language instructions, and the corresponding machine codes, of the RUN2223 CPU
  Occasionally, the descriptions in this manual were deliberately incomplete. In these cases it was up to us to make sensible design choices.
 2. A "template", which was basically a zipped folder containing:
    - .dig files for the components of the computer other than the CPU.
    - a subdirectory containing empty files we should use to build the subcomponents of the processor in.
    We were not allowed to change the structure of these files.

We did not get a "recipe" for designing the components, the only requirement and guideline was to build a processor out of "sensible" subcomponents that would implement the Instruction Set Architecture (ISA) of the RUN2223 CPU as given in the manual. So we designed:
 - the ALU, with subcomponents for:
    - Shiftleft, Rotateleft, Shiftright, Rotateright
 - the Flag Register Bank (containing flag registers for conditions)
 - the Register Bank
 - the Instruction Decoder
 - the Tester, which tested conditions based on the contents of the flag registers.
