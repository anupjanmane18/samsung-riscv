# samsung-riscv
##  Basic Details

**Name:** Anup Nagaraj Janmane  
**College:** KLE Institue of Technology  
**Email ID:** anupjanmane18@gmail.com  
**GitHub Profile:** [Anup_janmane_Github](https://github.com/anupjanmane18)  
**LinkedIN Profile:** [Anup_Janmane](https://www.linkedin.com/in/anup-janmane-a960b325b/)

----------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 1:</b>Task is to install all the essential tools required for this samsung-RISCV  Workshop such as Ubuntu on VMBox & refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler</summary><br>

### Install Ubuntu 20.04 LTS on Oracle Virtual Machine Box

Firstly, I have downloaded the virtual box from the links provided to us and
loaded a linux version with image dock file sent  
![Ubuntu and VMBox Installation](https://github.com/anupjanmane18/samsung-riscv/blob/main/task1/virtual_machine_installed.png)

### C Language based LAB
I have successfully run the virtual machine and compiled the tasks.

Initial task is:-

### write a program to compile the sum of first 5 natural numbers in c:

we have written the code sum of 1st 5 numbers in leafpad as shown below.

```
gcc sum_1ton.c

./a.out
```

this code will be run in terminal to get output as 15 for 1st 5 numbers as shown below :


![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task1/C%20Code%20compiled%20on%20gcc%20Compiler.png)

### RISCV based LAB

1. Using the cat command, the entire C code will be displayed on the terminal.
   
![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task1/cat%20Command.png)

2. A program is run to obtain risc-v version of the code previously written in c:

  	 ```
	riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c
	```

![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task1/RISCV_C_CODE_O1.png)


3. As the whole version of above code looks lengthier we have used below code to make it shorter
	
 	```
	riscv64 -unknown-elf-objdump -d sum1ton.o | less
	```
 
& we have obtained the required main part to compare the execution in assembly language as shown below :

	
 
![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task1/Objdump%20using%20-O1%20format.png)

4. Open the same terminal and run the given command:
 
 	```
	riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum_1ton.o sum_1ton.c
	``` 


![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task1/RISCV_CODE_Ofast.png)

5. As the whole version of above code looks lengthier as earlier we have used below code to make it shorter
	
 	```
	riscv64 -unknown-elf-objdump -d sum1ton.o | less
	```
 
& we have obtained the required main part to compare the execution in assembly language as shown below :



![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task1/Objdump%20using%20-Ofast%20format.png)

### End of 1st task
</details>

------------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 2:</b> Performing SPIKE Simulation and Debugging the C code with Interactive Debugging Mode using Spike.
	
I understood the principle and working of the whole program and how various registers like stack pointer and r5 are increasing & understood how the interface explains the process itself.
</summary> 

### What is SPIKE in RISCV?
* Spike is a free, open-source C++ simulator for the RISC-V ISA that models a RISC-V core and cache system. It can be used to run programs and a Linux kernel, and can be a starting point for running software on a RISC-V target.

### Testing the SPIKE Simulator for sum1ton.c
**spike_O1_objdump**

* Here we are compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-O1_format** using SPIKE simulator

![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task2/spike_O1_objdump_for_sum1ton.png)

* In the above picture registor a0 earlier has value 21000 in hex decimal.
* After running the registor a0 became 21180 in hexa decimal.
* * Because there has +384 in decimal,so after calculation it gives the above value 

**Spike_Ofast_objdump**

* Here also goes the same we compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-Ofast_format** using SPIKE simulator



![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task2/spike_Ofast_objdump_for_sum1ton.png)

* In the above picture registor sp earlier has value 3ffffffb50 in hex decimal.
* After running the registor a0 became 3ffffffb40 in hexa decimal.
* Because there has -16 in decimal,so after calculation it gives the above value.

### Multiplication of first n natural numbers (C program):

**Here i have used n value as 7**

![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task2/c_code_for_mult_on_gcc_Compiler.png)

**riscv_objdump_O1_format**

* we have obtained the required main part to compare the execution in assembly language as shown below :

![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task2/Objdump_using%20-O1_format_for_mult.png)

**riscv_objdump_Ofast_format**

* we have obtained the required main part to compare the execution in assembly language as shown below :

![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task2/Objdump_using%20-Ofast_format_for_mult.png)


### Testing the SPIKE Simulator for new c program i.e mult1ton.c
**spike_O1_objdump**

* Here we are compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-O1_format** using SPIKE simulator

![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task2/spike_O1_objdump_for_mult1ton.png)

* In the above picture registor a2 earlier has value 1000 in hex decimal.
* After running the registor a2 became 13b0 in hexa decimal.
* Because there has +944 in decimal,so after calculation it gives the above value. 

**Spike_Ofast_objdump**

* Here also goes the same we compare both of the compiler that must display the same output on the terminal.
* after that we are gona debug the sum1ton.c of **-Ofast_format** using SPIKE simulator



![image](https://github.com/anupjanmane18/samsung-riscv/blob/main/task2/spike_Ofast_objdump_for_mult1ton.png)

* In the above picture registor a0 earlier has value 21000 in hex decimal.
* After running the registor a0 became 21180 in hexa decimal.
* Because there has +384 in decimal,so after calculation it gives the above value.

### Steps to debug spike simulation

* bring the pointer to a starting location using
```
until pc 0 100b0(loaction address uh wish to)
```
* next get the value of the registor by using
```
reg 0 a2(your registor address)
```
* next run the next intrsuction by clicking Enter key.
* after that repeat the above instruction i.e **reg 0** instruction & compare the previous value and next value.


* I have used same for both O1_format & Ofast_formate in sum1ton.c & mult1ton.c files 

### End of 2nd task
</details>

------------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 3:</b> Task is to identify various instruction type of all the given instructions with its exact 32 bits instruction code. </summary>

### INSTRUCTIONS FORMAT IN RISC-V  
 
There are 6 instruction formats in RISC-V:  
1. R-format  
2. I-format  
3. S-format  
4. B-format  
5. U-format  
6. J-format

### 1. R-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In R-type instruction, R stands for register
* This instruction type is used to execute various arithmetic and logical operations.
* The entire 32 bits instruction is divided into 6 fields as shown below.
![R-type](https://github.com/maazm007/vsdsquadron-mini-internship/assets/83294849/4a17f03e-ae74-4809-a8d9-79924fb8b421)

### 2. I-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In I-type instruction, I stand for immediate which means that operations use Registers and Immediate value
* This instruction type is used in immediate and load operations.
*  The entire 32 bits instruction is divided into 5 fields as shown below.

![I-type](https://github.com/maazm007/vsdsquadron-mini-internship/assets/83294849/4a53f5fa-d55a-4308-8f93-a0f2f3aedba0)

**Example: ADDI rd, rs1, imm**


### 3. S-type Instruction  

* In RV32, each instruction is of size 32 bits.
*  In S-type instruction, S stand for store which means it is store type instruction that helps to store the value of register into the memory.
*  Mainly, this instruction type is used for store operations.
*  The entire 32 bits instruction is divided into 6 fields as shown below.  
  
![s-type](https://github.com/maazm007/vsdsquadron-mini-internship/assets/83294849/fc9ddedc-4c99-4b6f-9765-c2e8c8e29302)

**Example: SW rs2, imm(rs1)**


### 4. B-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In B-type instruction, B stand for branching which means it is mainly used for branching based on certain conditions.
*  The entire 32 bits instruction is divided into 8 fields as shown below.  
  
![B-type](https://github.com/maazm007/vsdsquadron-mini-internship/assets/83294849/14486f41-f3e4-4c4a-85b0-9acc56be3f46)

**Example: BEQ rs1, rs2, imm**   
 
  
### 5. U-type Instruction  
* In RV32, each instruction is of size 32 bits.
*  In U-type instruction, U stand for Upper Immediate instructions which means it is simply used to transfer the immediate data into the destination register.
*  The entire 32 bits instruction is divided into 3 fields as shown below.  
  
![u-type](https://github.com/maazm007/vsdsquadron-mini-internship/assets/83294849/4f3df58b-8c0c-45c6-ba39-a196547dd38f)

**Example: LUI rd, imm**   

  
### 6. J-type Instruction  
* In RV32, each instruction is of size 32 bits.
* In J-type instruction, J stand for jump, which means that this instruction format is used to implement jump type instruction.
*  The entire 32 bits instruction is divided into 6 fields as shown below.  
  
![j-type](https://github.com/maazm007/vsdsquadron-mini-internship/assets/83294849/5dc9a9be-4048-4a35-a99e-7b4a0075caa0)

**Example: JAL rd, imm**


