# Week13
## Computer
* [computer.hdl](https://github.com/mark456tung/co109a/blob/master/05/Computer.hdl)
* [ComputerAdd.out](https://github.com/mark456tung/co109a/blob/master/05/ComputerAdd.out)
* [ComputerAdd-external.out](https://github.com/mark456tung/co109a/blob/master/05/ComputerAdd-external.out)
* [ComputerMax.out](https://github.com/mark456tung/co109a/blob/master/05/ComputerMax.out)
* [ComputerMax-external.out](https://github.com/mark456tung/co109a/blob/master/05/ComputerMax-external.out)
* [ComputerRect.out](https://github.com/mark456tung/co109a/blob/master/05/ComputerRect.out)
* [ComputerRect-external.out](https://github.com/mark456tung/co109a/blob/master/05/ComputerRect-external.out)
```
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/05/Computer.hdl

/**
 * The HACK computer, including CPU, ROM and RAM.
 * When reset is 0, the program stored in the computer's ROM executes.
 * When reset is 1, the execution of the program restarts. 
 * Thus, to start a program's execution, reset must be pushed "up" (1)
 * and "down" (0). From this point onward the user is at the mercy of 
 * the software. In particular, depending on the program's code, the 
 * screen may show some output and the user may be able to interact 
 * with the computer via the keyboard.
 */

CHIP Computer {

    IN reset;

    PARTS:
    // Put your code here:
    ROM32K(address=pc,out=instruction);
    CPU(inM=inM,instruction=instruction,reset=reset,writeM=writeM,outM=outM,addressM=addressM,pc=pc);
    Memory(in=outM,address=addressM,load=writeM,out=inM);

}
```
![computer](https://github.com/mark456tung/co109a/blob/master/picture/computer.png)
