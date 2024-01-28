Name: Brandon Hoover
Username: bch60 - PeopleSoft#: 4603007
Email: bch60@pitt.edu
All instructions and components work as shown in 100% autograder score.
No known problems with design

---------------------------------------

Control Component Signals (chronological Order): Control is above Reg file as labled

1. halt - used in halt instruction to stop fetch operation from Instruction memory (ROM)
\
2. Jump - signifies that a jump instruction was read by ROM and should attempt to be executed. Used in Jump Section Multiplexer to show that you sould not just send PC + 1 to Instruction Memory.
\
3. Useless 2 - Has no functionality, was apart of a previous attempt and did not want to mess up the output signals that were already formatted.
\
4. MemRead - Used in Data Memory section (RAM) - if 1 then read from memory (lw) 
\
5. Useless - Same as Useless 2 ¯\_(ツ)_/¯
\
6. ALUOp - the Opcode for the ALU that determines with arithmetic operation to run inside of the ALU, default is NAND (000)
\
7. MemWrite - Used in Data Memory section (RAM) - if 1 then write the data from a register to memory
\
8. ALUSrc - stands for ALU source i.e if the data that is going into input B of the ALU is coming from a register or an immediate value passed in
\
9. RegWrite - Write Enable - if 1 then you can write data to a register
\
10. putEnable - if 1 then outputs value of put register that was read in from RS
\
11. signExt - if 1 then instead of zero extending the immediate value, you sign extend it. Which means that if the immediate start with a 1 then you extend the 1's to the new value.
\
12. WriteDataSel - Used in the section to the right of the RAM component which determines from which source the data that you are writing to a register RS from. Is an Opcode and can find Priority encoder inside of Control
\
13. branchOp - opcode for branch logic decoder. If branch instruction used and condition is true, then sends a 1 to multiplexer before PC that performs the branch. default output is 0 (blank)
\
14. JumpOp - opcode for jump logic multiplexer. If jump instruction used, determines which one was used and executes the instruciton. 

---------------------------------------

Notes and strategy used:

I began by comparing the diagram provided in the powerpoint of the 32 bit MIPS CPU and trying to recreate a version of that in Logisim. Also started on the RegFile and ALU since skelotons were provided.

After that I decided to move left and implement the instruction splitter, I know it adds a lot of wires to not do this a subciruit but it just 1 - looks way cooler this way and 2 - helps me trace control flow a lot easier

Then I moved upward worked on the Control which was the hardest to wrap my head around, aligned output pins and labled priority encoders used. 

Next was the RAM and ROM components that saw the first execution of machine code and getting the halt and puts functions working. Puts circuit elements are on the far right.

Lastly after fixing zero extension versus sign extension, and fixing mul and div in the ALU, I worked on branching that would make my PC section look like a mess (far left) but still works efficiently.

I guess the jump section can also be included in that since they are similar. One central clock at the bottom hooking up the components, this project was VERY educational, for better or worse. 