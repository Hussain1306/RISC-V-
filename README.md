# RISC-V-OPEN-SOURCE
Hi,
My name is Syed Jalaluddin Hussain Naqvi. This is my RISC-V Open Source Project. Its an open standard instruction set architecture (ISA) based on established reduced instruction set architecture (RISC) principles. Examples of RISC architecture includes MIPS, POWER PC, Microchip PIC, Arm and many more. Its first time designed in 2010 


**Description**

This is RISC-V  32-bit ISA. It contains Register file which is consist of 32 registers of 32-bit, ALU which performs all arithmetic operations, Decoder which decodes the instructions and give it to their  respective components, Immediate Generator which generates immediate of respective type  with the help of PC and instructions,  PC means program counter which normally increase with by 4 until any specific instruction given, Control  Unit gets three things opcode,FN3 and 30th bit of FN7 it is basically based on two sub component (Type Decode and Control Decode) which tells us what type instruction it is and what to do with it and it further passes to Register file or ALU  or Branch select or  Memory. Further we will discuss when we see how it works.


**Components**

1.	PC
2.	Decoder
3.	Control Unit
4.	Immediate Generator
5.	Register File
6.	ALU
7.	Main Memory
8.	Branch Selector


**Software**

•	Logisim   Logisim.

•	Venus  Simulator Venus

•	Github Github


**Designing**

First of all make 32-bit ISA of RISC V on logisim or any other which can be supported.  For this we have used PC by 32-bit register, Decoder by using ROM, Control unit of 32-bit which is composed on further two components type decode and control decode, Register file by using 32 registers of 32-bit, ALU ,Main Memory, separate branch selector by using comparator’s for conditions of branches and Immediate generator  for their respective types. We have used tunnels to avoid long and complex wirings. Beside these things its not enough and incomplete so we have used multiplexers, splitters, clocks and adders to complete this circuit. 


**Working**

Now we can see the working of this ISA by implementing this assembly code on venus:

addi x4 zero 15

addi x5 zero 20

add x6 x5 x4

we also got this on venus  hexa-decimal value is:

0x00F00213

0x01400293

0x00428333

When you copy the hexa-decimal value and write down in notepad kindly remove ”0x” from the start of every value.
The PC starts with 0 and increase by offsets of 4 because in this code no specific command used like jal , jalr or branches or any other.  Then decoder decodes it and send it to register file while one wire of PC and decoder also connected with Immediate generator which gives immediate to its respective type. Control unit deicides which types of instruction it is and sends it to their respective places . Control unit sends signal to register file which is already connected to decoder splitter. The register file sends the value of source register and Immediate both  goes to ALU. Then ALU performs arithmetic operations and gives to destination register. This cycle again repeat fornext instruction because both are same tpe and for third one just immediate generator escape out and both values goes from register file by source registers and again ALU perform arithmetic operation and gives to destination register.


**Instructions Supported:**

1.	add
2.	addi
3.	sub
4.	or
5.	ori
6.	xor
7.	xori
8.	and
9.	andi
10.	slt
11.	sltu
12.	sll
13.	srl
14.	sra
15.	srai
16.	jal
17.	jalr
18.	slli
19.	srl
20.	srli
21.	srai
22.	slti
23.	sltiu
24.	lb
25.	lh
26.	lw
27.	sb
28.	sh
29.	sw
30.	auipc
31.	lui
32.	li
33.	beq
34.	bne
35.	blt
36.	bge
37.	bltu
38.	bgeu



