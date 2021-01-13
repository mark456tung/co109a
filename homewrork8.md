# Week9
## mult
* [mult.asm](https://github.com/cycyucheng1010/co109a/blob/master/04/mult/mult.asm)
```
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/04/Mult.asm

// Multiplies R0 and R1 and stores the result in R2.
// (R0, R1, R2 refer to RAM[0], RAM[1], and RAM[2], respectively.)

// Put your code here.

@2    // R2=0
M=0
@0   //R0=M 
D=M
@50  //IF R0=0 , JUMP TO R50  0*ANY=0
D;JEQ 
@1  //R1=M
D=M
@50 //IF R1=0,JUMP TO R50 ANY*0=0
D;JEQ
@12 //LOOP 
D;JNE
@0
D=M
@2
M=M+D // mult=>a=a+b do x times 
@1
M=M-1
D=M
@12 //LOOP
D;JNE
```
## hack
* [mult.hack](https://github.com/mark456tung/co109a/blob/master/04/mult/Mult.hack)

![hack.png](https://github.com/mark456tung/co109a/blob/master/04/mult/mult1.PNG)
## RESULT
* [mult.out](https://github.com/mark456tung/co109a/blob/master/04/mult/Mult.out)
![mult.png](https://github.com/mark456tung/co109a/blob/master/04/mult/mult2.PNG)