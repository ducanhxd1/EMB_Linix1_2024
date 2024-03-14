### 1. COMPILER
> https://www.geeksforgeeks.org/compiling-a-c-program-behind-the-scenes/

**1, How do we compile and run a C program?**

-> Step 1: Creating a C Source File

-> Step 2: Compiling using GCC compiler

-> Step 3: Executing the program

**2, What is the compilation?**

The compilation is the process of converting the source code of the C language into machine code. 

C is a mid-level language, it needs a compiler to convert it into an executable code so that the program can be run on our machine.

**3, What goes inside the compilation process?**

<img width="600" alt="image" src="https://github.com/minchangggg/AdvancedC/assets/125820144/bce15492-bcab-4c06-aae9-b77140e00075">

**a, Preprocessor**

<img width="200" alt="image" src="https://github.com/minchangggg/AdvancedC/assets/125820144/7f77b474-8ea0-43d6-875a-65d38ccfc701">


<img width="500" alt="image" src="https://github.com/minchangggg/AdvancedC/assets/125820144/0e3464b8-1928-46bb-87ef-f719093c721d">

<img width="700" alt="image" src="https://github.com/minchangggg/AdvancedC/assets/125820144/c4392f1b-c42e-4fb6-ad13-514f92181ba2">


**b, Compiler** 

The compiler takes the preprocessed file and uses it to generate corresponding assembly code. 

<img width="200" alt="image" src="https://github.com/minchangggg/AdvancedC/assets/125820144/cba3c714-7fb1-4289-bf20-b31dedd5950d">

<img width="700" alt="image" src="https://github.com/minchangggg/Advanced_C/assets/125820144/572bbb3e-4c88-46aa-87b0-b83096c05db3">

=> This file is in assembly-level instructions.

**c, Assembler**

Assembles the code into object code 

< Where assembly code represents a correspondence between program and machine code, object code represents pure machine code (ie. binary) >

<img width="200" alt="image" src="https://github.com/minchangggg/Advanced_C/assets/125820144/d5cc0269-704f-47e2-8836-8be945268cd6"> => This file contains machine-level instructions.

<img width="700" alt="image" src="https://github.com/minchangggg/Advanced_C/assets/125820144/d3b1bed3-c128-4302-98ca-402b2cf02bbf">


**d, Linker**

<img width="200" alt="image" src="https://github.com/minchangggg/AdvancedC/assets/125820144/7d3880db-b0b7-46e9-8c31-21035966c67e">


<img width="250" alt="image" src="https://github.com/minchangggg/Advanced_C/assets/125820144/973c3ae7-18ae-4786-939b-11fa524098ec">
