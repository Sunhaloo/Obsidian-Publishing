---
Alias: Programming Techiques Tutorial 1 - Week 1
Tag: uni, theory
Module: BSNC1102C
Author: S.Sunhaloo
Date: 2024-05-21
Status: Completed
---

<p align="center">Programming Techniques<br>Tutorial 1<br>BCNS1102C<br>SUNHALOO Shehzaad</p>

<p align="center">University of Technology, Mauritius</p>

---

### My Links

- [[Programming Questions - Tutorial 1#Socials | Link to Social]]

---

>[!tip] 1 Distinguish between Hardware and Software.
>Hardware is the tangible part of the computer like the:
>- Processor / Central Processing Uni ( CPU )
>- Random Access Memory ( RAM ) Stick
>- Power Supply Unit ( PSU )
>- Motherboard
>Software are the intangible programs and data that runs on the computer's hardware, software can include:
>- System Software
>	- BIOS
>	- Operating System ( Linux [ *arch, debian, nix* ], Windows )
>- Application Software
>	- Software that runs "*on*" the OS and hardware
>- Utility Software
>	- Disk Defragmentation
>	- Disk Cleaner
>	- Firewall

>[!tip] 2 What are the main components of a computer?
>Components can be classified as **INPUT**, **PROCESS** and **OUTPUT**
>**INPUT** components: Keyboard, Mouse, Gamepad, Stylus
>**PROCESS** components: CPU, GPU, RAM, Storage Devices
>**OUTPUT** components: Monitor, Printer, Speakers
>Miscellaneous components includes: Power Supply Unit, Case, CPU Cooler / AiO.

>[!tip] 3 What does the CPU stands for and what is its role?
>CPU = Central Processing Unit
>It is the "*brain*" of the computer; its role is to **process** data and **execute** programs.

>[!tip] 4 With the help of appropriate examples distinguish between primary ( main ) and secondary memory?
>**Primary** Memory is a memory that is directly and continuously being accessed by the CPU while the **Secondary** memory can also be accessed by the CPU but mostly used for reading and writing data into permanent storage.
>Primary Memory: RAM, ROM
>Secondary Memory: Storage devices like Disks ( external HDD ).
>![[CPU - Memory - Input - Output.png | 400]]

>[!tip] 5 Write down all the Bit Permutations of 3 bits and 4 bits.
>3 Bits $\Rightarrow$ 8 Combinations | 4 Bits $\Rightarrow$ 16 Combinations
>
>| 3 Bits | 4 Bits |
>| ------ | ------ |
>| 000 | 0000 |
>| 001 | 0001 |
>| 010 | 0010 |
>| 100 | 0100 |
>| 011 | 1000 |
>| 101 | 0011 |
>| 110 | 0101 |
>| 111 | 1001 |
>|  | 1010 |
>|  | 0110 |
>|  | 1100 |
>|  | 0111 |
>|  | 1011 |
>|  | 1101 |
>|  | 1110 |
>|  | 1111 |

>[!tip] 6 How many items can be represented by 8 bits?
>8 Bits $\Rightarrow \ 2^{8} = 256$ in the range of  0 - 255.

>[!tip] 7 One terabyte is the power of <ins style="font-weight: bold">___</ins>?
>1 TB = $2^{40} \leftarrow$ Answer
>1 TB = 1024 GB
>1024 GB $\Rightarrow$ 1024 $\times$ 1024 MB = 1048476 MB
>1048476 MB $\Rightarrow$ 1048476 $\times$ 1024 KB = 1073741824 KB
>1073741824 KB $\Rightarrow$ 1073741824 $\times$ 1024 B = 1099511627776 B
>1099511627776 B $\Rightarrow$ 1073741824 $\times$ 8 bits = 8796093022208 bits

>[!tip] 8 What are the 3 main modules that consist in the CPU in and what are their roles?
>The 3 modules are:
>1. Arithmetic Logic Unit
>	- Performs mathematical calculations ( *addition, subtraction, multiplication, division* ) and operations ( *AND, OR, NOT, XOR* )
>2. Control Unit
>	- Controls the flow of data / executes operations or instructions.
>3. Registers
>	- Small temporary memory that stores data that is currently being used ( *processed* ) by the CPU
>	- Examples of registers:
>		- Program Counter ( PC )
>		- Memory Address Register ( MAR )
>		- Memory Data / Buffer Register ( MDR )
>		- Current Instruction Register ( CIR )

>[!tip] 9 Name and briefly describe the four programming language levels providing suitable examples of each.
>>From highest level $\rightarrow$ lowest level
>- High Level Language
>	- English like syntax $\Rightarrow$ Extremely code to the human language
>	- Examples: Python, Java, Go
>- Low Level Language
>	- Examples: C, C++, C#, Rust
>- Assembly Language
>	- Close to Machine code but still readable by a human being
>- Machine Code
>	- Only understood by the computer
>	- Consists of `0` and `1` / String of 0's and 1's
>##### Example of High Level Language
>```python
>import random as rd
>print()
>for x in range(5):
>    for y in range(2):
>        x = rd.randint(0, 9)
>        print(x, end="", flush=True)
>    print()
>print()
>```
>
>##### Example of Low Level Language
>```C
>#include <stdio.h>
>
>int main() {
>
>	// DECLARE ARRAY name[4]: INTEGER
>	char name[5] = {1, 2, 3, 4, 5};
>
>	printf("Contents of Array\n");
>
>	for(int i = 0; i < 5; i++){
>		printf("Index: %d | Value = %d\n", i, name[i]);
>	}
>
>}
>```
>##### Example of Assembly Language
>```console
>STO 34
>LDD 101
>MOV 203
>ADD 101
>```

>[!tip] 10 What is a compiler and what is its function?
>A compiler is a program that translate high-level language / low-level language / source code into machine code ( *object code* ) **all** at *once* so that the computer can understand.
>- Create an executable `.exe`
>- Produces an error list
>- Consumes a lot of memory ( *if source code is pretty big* )
>- Example of compiler:
>	- gcc, rustc, javac
>>"*source code*": Code written by the Programmer

>[!tip] 11 How do you differentiate between a compiler and an interpreter?
>The compiler will convert the source code into machine code **all** at *once* while the interpreter will convert each line of the source code ( **line-by-line translation** ).
>The compiler is normally used to create the final "*program*" while the interpreter is used during the development of the program
>-Interpreter
>	- Does not create `.exe` file
>	- Stop as soon as it encounters an error
>	- Faster; does not consumes much memory compared to compiler


>[!tip] 12 Name and describe with the help of suitable examples of 3 types of errors that a program can contain.
>- Syntax Error
>	- Example
>		- Instead of typing `printf()`; someone types `prntf()`
>- Runtime Error
>	- Example
>		- Opening a file that is not present in path
>		- Division by 0
>- Logic Error
>	- Example
>		- If we need to calculate if `a` $\gt$ `b`; if `a` is **actually** $\gt$ `b`, but the programmer outputs:
>			- `b is greater than a`

>[!tip] 13 What is the name of the machine language for the Java Virtual Machine ( JVM )?
><span style="color: red;">Bytecode</span>!
>>[!info]
>>After running `javac Main.java` / the compiler; it will create the bytecode.

>[!tip] 14 Describe what is an algorithm? Support you answer with an example.
>An algorithm is a set of **finite** instructions that will carry out a specific task ( *by a computer* ), step by step, to solve a problem.
>- Example:
>	- Binary Search
>		- Fast, searching algorithm to search in large arrays / lists
>	- Bubble Sort
>		- Slow sorting algorithm used to sort arrays

>[!tip] 15 How do you differentiate between an algorithm and a flowchart?
>A **flowchart** consists of ( *mostly* ) diagrams while an algorithm is more "*written*".
>>From what I can say its that it is mostly a *graphical* v/s *written* approach.

>[!tip] 16 Draw the 7 standard symbols which are used in flowcharts and explain briefly the purpose of each of these.
>![[Flowchart Symbols.png]]

---

# Socials

- [**Instagram**](https://www.instagram.com/s.sunhaloo/)
- [**YouTube**](https://www.youtube.com/channel/UCMkQZsuW6eHMhdUObLPSpwg)
- [**GitHub**](https://www.github.com/Sunhaloo)

---

S.Sunhaloo
Thank You!