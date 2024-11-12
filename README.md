java c
CS210 Fall 2024: PS2A 
Multiple Choice
1. (1 point) How do registers differ from Main Memory in a computer system ?
Registers are smaller and faster but used for short-term storage, while Main Memory is larger and slower but used for long-term storage.
Registers are used only for storing data.
Main Memory is directly connected to the CPU, while registers are not.
All of the above.
None of the above.
2. (1 point) In an x86 machine, variables and other data values in assembly programs are typically stored in the ’text’ section.
True.
False.
3. (1 point) In most CPUs, instructions are executed sequentially by default.
True
False
4. (1 point) The linker
Can produce an executable.
Takes as input fragments of an executable in the form. of object files.
Combines all of the data bytes of a program into a single data section.
Combines all of the text bytes of a program into a single text section.
All of the above.
None of the above.
5. (1 point) How do “jump” (jmp) instructions contribute to program control flow ?
They force the CPU to execute the same sequence of instructions repeatedly.
They allow for conditional execution of code.
They enable the CPU to transfer control to a different address in memory.
All of the above.
None of the above.
6. (1 point) Select the correct answer:
The PC register and IR register are general-purpose registers.
The PC register is used to hold the instruction of the opcode to be executed.
The PC register stores the memory address of the operation to be executed.
All of the above.
None of the above.
7. (1 point) Which of the following best describes the sequence of internal phases of generic CPU pro-gram execution?
I: Get the value at the location pointed to by the PC 
II: CPU conducts memory bus transactions to write results of a calculation to main memory 
III: Identify operation and location of input and output values 
I, II, III.
II, I, III.
I, III, II.
None of the above.
Basic Byte Representation 
The following is the gdb dump of 64 bytes of memory in base 2 notation. Using this data please fill in the following tables.
0 x402000 : 01000011 01010011 00100000 00110010 00110001 00110000 00111100 00110011
8. (4 points) Write the values as single byte values in hex notation.
0x402000
9. (4 points) As 2-代 写CS210 Fall 2024: PS2AWeb
代做程序编程语言byte little endian values in hex notation.
0x402000
10. (4 points) As 4-byte little endian values in hex notation.
0x402000
11. (4 points) As an 8-byte little endian value in hex notation.
0x402000
12. (4 points) Finally using the provided ASCII Table please fill in the table below translating each byte into an ascii character.
0x402000
Assembly Fragments 
Given the code and list of gdb commands below, answer the following questions. Assume the code has been assembled and linked correctly to produce a binary, after which gdb is used with the binary to run the given gdb commands.
Remember to use Little Endian byte ordering for multi-byte values when displayed as single bytes 
13. Assembly code for subsum.S:
1 . i n t e l s y n t a x n o p r e f i x
2 . s e c t i o n . d a t a
3
4 v a l u e 1 : . quad 0x4
5 v a l u e 2 : . quad 0x8
6
7 . s e c t i o n . t e x t
8 . g l o b a l _s t a r t
9
10 _s t a r t :
11 sub rax , QWORD PTR [ v a l u e 1 ]
12 cmp rax , 0
13 j g B
14 A:
15 add rax , QWORD PTR [ v a l u e 1 ]
16 B :
17 add rax , QWORD PTR [ v a l u e 2 ]
18 C :
19 i n t 3
Gdb commands used with the binary subsum produced from subsum.S.
1 f i l e subsum
2 s e t d i s a s s e m b l y − f l a v o r i n t e l
3 b _s t a r t
4 run
5 d e l e t e 1
6 s e t $r a x = 3
7 s i
8 s i
9 s i
10 s i
11 s i
12 p / x $r a x
13 p / x $pc
14 x / 1 xg v a l u e 2
15 x / 8 xb v a l u e 2
16 q u i t
Addtionally this is the gdb output for the gdb command at line 3 of the above commands:
1 ( gdb ) x / 6 i
s t a r t
2 0 x401000 < s t a r t >: sub rax ,QWORD PTR ds : 0 x402000
3 0 x401008 < s t a r t +8>: cmp rax , 0 x0
4 0 x40100c < s t a r t +12>: j g 0 x401016   
5 0 x40100e : add rax ,QWORD PTR ds : 0 x402000 
6 0 x401016 : add rax ,QWORD PTR ds : 0 x402008 
7 0 x40101e : i n t 3 
(a) (2 points) Value displayed for rax on line 12 of gdb commands: 
(b) (2 points) Value displayed for pc on line 13 of gdb commands: 
(c) (2 points) Value displayed for line 14 of gdb commands: 
(x/1xg value2 means display one 64bit value at the address in memory of the value2 sym-bol in hex notation) 
(d) (1 point) Values displayed on line 15 of gdb commands: 







         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
