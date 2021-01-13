# WEEK1
## Not
![not](https://github.com/mark456tung/co109a/blob/master/picture/not.png)

* [Not.hdl](https://github.com/mark456tung/co109a/blob/master/01/Not.hdl)
* [Not.out](https://github.com/mark456tung/co109a/blob/master/01/Not.out)
<pre><code>
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Not.hdl

/**
 * Not gate:
 * out = not in
 */

CHIP Not {
    IN in;
    OUT out;

    PARTS:
    // Put your code here:
    Nand(a=in, b=in, out=out);
}
</code></pre>
## And
![and](https://github.com/mark456tung/co109a/blob/master/picture/and.png)

* [And.hdl](https://github.com/mark456tung/co109a/blob/master/01/And.hdl)
* [And.out](https://github.com/mark456tung/co109a/blob/master/01/And.out)
<pre><code>
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/And.hdl

/**
 * And gate: 
 * out = 1 if (a == 1 and b == 1)
 *       0 otherwise
 */

CHIP And {
    IN a, b;
    OUT out;

    PARTS:
    // Put your code here:
    Nand(a=a,b=b,out=AnandB);
    Not(in=AnandB,out=out);

}
</code></pre>
## Or
![or](https://github.com/mark456tung/co109a/blob/master/picture/or.png)

* [Or.hdl](https://github.com/mark456tung/co109a/blob/master/01/Or.hdl)
* [Or.out](https://github.com/mark456tung/co109a/blob/master/01/Or.out)
<pre><code>
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Or.hdl

 /**
 * Or gate:
 * out = 1 if (a == 1 or b == 1)
 *       0 otherwise
 */

CHIP Or {
    IN a, b;
    OUT out;

    PARTS:
    // Put your code here:
    Not(in=a,out=na);
    Not(in=b,out=nb);
    Nand(a=na,b=nb,out=out);

}
</code></pre>

## Xor
![not](https://github.com/mark456tung/co109a/blob/master/picture/xor.png)
* [Xor.hdl](https://github.com/mark456tung/co109a/blob/master/01/Xor.hdl)
* [Xor.out](https://github.com/mark456tung/co109a/blob/master/01/Xor.out)
<pre><code>
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Xor.hdl

/**
 * Exclusive-or gate:
 * out = not (a == b)
 */

CHIP Xor {
    IN a, b;
    OUT out;

    PARTS:
    // Put your code here:
    Not(in=a, out=na);
    Not(in=b, out=nb);
    And(a=a, b=nb ,out=c);
    And(a=na, b=b, out=d);
    Or(a=c, b=d, out=out); 
}
</code></pre>
## Mux
![not](https://github.com/mark456tung/co109a/blob/master/picture/mux.png)
* [Mux.hdl](https://github.com/mark456tung/co109a/blob/master/01/Mux.hdl)
* [Mux.out](https://github.com/mark456tung/co109a/blob/master/01/Mux.out)
<pre><code>
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/Mux.hdl

/** 
 * Multiplexor:
 * out = a if sel == 0
 *       b otherwise
 */

CHIP Mux {
    IN a, b, sel;
    OUT out;

    PARTS:
    // Put your code here:
    Not(in=sel, out=nsel);
    And(a=a,b=nsel,out=c);
    And(a=b,b=sel,out=d);
    Or(a=c,b=d,out=out);
}
</code></pre>
## DMux
![not](https://github.com/mark456tung/co109a/blob/master/picture.dmux.png)
* [Mux.hdl](https://github.com/mark456tung/co109a/blob/master/01/Mux.hdl)
* [Mux.out](https://github.com/mark456tung/co109a/blob/master/01/Mux.out)
<pre><code>
// This file is part of www.nand2tetris.org
// and the book "The Elements of Computing Systems"
// by Nisan and Schocken, MIT Press.
// File name: projects/01/DMux.hdl

/**
 * Demultiplexor:
 * {a, b} = {in, 0} if sel == 0
 *          {0, in} if sel == 1
 */

CHIP DMux {
    IN in, sel;
    OUT a, b;

    PARTS:
    // Put your code here:
    Not(in=sel,out=nsel);
    And(a=in, b=nsel, out=a);
    And(a=in, b=sel, out=b);
}
</code></pre>



