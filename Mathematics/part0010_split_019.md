Chapter 10    

##[Introduction](part0010_split_019.md)

You can use a computer algebra system (CAS) to manipulate complicated math expressions and solve any equation.

All computer algebra systems offer essentially the same functionality, so it doesn’t matter which system you use: there are free systems like `SymPy`, `Magma`, or `Octave`, and commercial systems like `Maple`, `MATLAB`, and `Mathematica`. This tutorial is an introduction to `SymPy`, which is a _symbolic_ computer algebra system written in the programming language Python. In a symbolic CAS, numbers and operations are represented symbolically, so the answers obtained are exact. For example, the number ![\sqrt{2}](00056.jpeg) is represented in `SymPy` as the object `Pow(2,1/2)`, whereas in _numerical_ computer algebra systems like `Octave`, the number ![\sqrt{2}](00056.jpeg) is represented as the approximation ![1.41421356237310](00237.jpeg) (a `float`). For most purposes the approximation is okay, but sometimes approximations can lead to problems: `float(sqrt(2))*float(sqrt(2)) = 2.00000000000000044` ![\neq 2](00238.jpeg). Because `SymPy` uses exact representations, you’ll never run into such problems: `Pow(2,1/2)*Pow(2,1/2)`![= 2](02865.jpeg).

This tutorial presents many explanations as code snippets. Be sure to try the code examples on your own by typing the commands into `SymPy`. It’s always important to verify for yourself!
