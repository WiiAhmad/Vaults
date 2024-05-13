Chapter 10    

##[Using SymPy](part0010_split_020.md)

The easiest way to use `SymPy`, provided you’re connected to the internet, is to visit[`http://live.sympy.org`](./live.sympy.org.md). You’ll be presented with an interactive prompt into which you can enter your commands—right in your browser.

If you want to use `SymPy` on your own computer, you must first install Python and the Python package `sympy`. You can then open a command prompt and start a Python session using:

you@host> python
Python X.Y.Z 
\[GCC a.b.c (Build Info)\] on platform
Type "help", "copyright", or "license" for more information.
>>> 

The `>>>` prompt indicates you’re in the Python shell which accepts Python commands. Type the following in the Python shell:

\>>> from sympy import \*
>>> 

The command `from sympy import *`![\;](02866.jpeg) imports all the `SymPy` functions into the current namespace. All `SymPy` functions are now available to you. To exit the python shell press `CTRL+D`.

For an even better experience, you can try `jupyter notebook`, which is a web interface for accessing the Python shell. Search the web for “jupyter notebook” and follow the installation instructions specific to your operating system. It’s totally worth it!

begins with a python `import` statement for the functions used in that section. If you use the statement `from sympy import *`   in the beginning of your code, you don’t need to run these individual import statements, but I’ve included them so you’ll know which `SymPy` vocabulary is covered in each section.
