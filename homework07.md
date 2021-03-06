# Week8
## PC
![pc](https://github.com/mark456tung/co109a/blob/master/picture/pc%20(program%20counter).png)
* [PC.hdl](https://github.com/mark456tung/co109a/blob/master/03/a/PC.hdl)
* [PC.out](https://github.com/mark456tung/co109a/blob/master/03/a/PC.out)
<pre><code>
  
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/03/a/PC.hdl

/**
 * A 16-bit counter with load and reset control bits.
 * if      (reset[t] == 1) out[t+1] = 0
 * else if (load[t] == 1)  out[t+1] = in[t]
 * else if (inc[t] == 1)   out[t+1] = out[t] + 1  (integer addition)
 * else                    out[t+1] = out[t]
 */

CHIP PC {
    IN in[16],load,inc,reset;
    OUT out[16];

    PARTS:
    // Put your code here:
    Inc16(in=PC,out=I16);
    Mux16(a=PC,b=I16,sel=inc,out=M1);
    Mux16(a=M1,b=in,sel=load,out=M2);
    Mux16(a=M2,b=false,sel=reset,out=M3);
    Register(in=M3,load=true,out=PC,out=out);
}
</pre></code>
